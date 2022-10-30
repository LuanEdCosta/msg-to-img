<script lang="ts">
  import Result from './Result.component.svelte'
  import Params from './Params.component.svelte'
  import Preview from './Preview.component.svelte'

  let title = 'Title'
  let subtitle = 'Subtitle'
  let color = '#5e67ec'
</script>

<main class="h-full w-full bg-stone-50 py-6 sm:py-8 lg:py-12">
  <div class="w-full max-w-screen-xl px-4 md:px-8 mx-auto flex flex-col gap-12">
    <div class="flex flex-col gap-2">
      <h1 class="text-3xl sm:text-5xl font-extrabold">Message To Image</h1>
      <p class="text-lg text-gray-600">Convert a text message into an image.</p>
    </div>

    <div class="grid lg:grid-cols-2 gap-6">
      <Preview {title} {subtitle} {color} />
      <Params bind:title bind:subtitle bind:color />
    </div>

    <Result />
  </div>
</main>
