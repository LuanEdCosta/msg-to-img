<script lang="ts">
  import html2canvas from 'html2canvas'
  import {
    copyImageToClipboard,
    canCopyImagesToClipboard,
  } from 'copy-image-clipboard'

  import Result from './Result.component.svelte'
  import Params from './Params.component.svelte'
  import Preview from './Preview.component.svelte'
  import Controls from './Controls.component.svelte'

  const canCopyImage = canCopyImagesToClipboard()

  let title = 'Title'
  let subtitle = 'Subtitle'
  let background = '#5e67ec'
  let color = '#ffffff'
  let result = ''

  async function handleGenerateImage() {
    const preview = document.getElementById('preview')
    const canvas = await html2canvas(preview)
    result = canvas.toDataURL()
  }

  async function handleCopyImage() {
    await copyImageToClipboard(result)
  }

  function handleDiscardImage() {
    result = ''
  }
</script>

<main class="min-h-screen bg-stone-50 py-6 sm:py-8 lg:py-12">
  <div class="w-full max-w-screen-xl px-4 md:px-8 mx-auto flex flex-col gap-12">
    <div class="flex flex-col gap-2">
      <h1 class="text-3xl sm:text-5xl font-extrabold">Message To Image</h1>
      <p class="text-lg text-gray-600">Convert a text message into an image.</p>
    </div>

    <div class="grid lg:grid-cols-2 gap-6">
      <Preview {title} {subtitle} {background} {color} />

      <Params
        bind:title
        bind:subtitle
        bind:background
        bind:color
        {handleGenerateImage}
      />
    </div>

    {#if result}
      <div class="grid lg:grid-cols-2 gap-6">
        <Result {result} />
        <Controls {canCopyImage} {handleCopyImage} {handleDiscardImage} />
      </div>
    {/if}
  </div>
</main>
