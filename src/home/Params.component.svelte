<script lang="ts">
  export let title: string
  export let subtitle: string
  export let background: string
  export let color: string
  export let handleGenerateImage: () => Promise<void>
</script>

<form
  class="flex flex-col gap-6 border border-gray-300 bg-white rounded-lg p-4"
  on:submit|preventDefault={handleGenerateImage}
  novalidate
>
  <div class="flex flex-col gap-2">
    <label for="title" class="font-bold w-full">Title</label>

    <input
      id="title"
      type="text"
      placeholder="Type a Title"
      class="h-12 px-4 outline-none bg-gray-50 focus:bg-gray-100 rounded-md"
      bind:value={title}
    />
  </div>

  <div class="flex flex-col gap-2">
    <label for="subtitle" class="font-bold w-full">Subtitle</label>

    <input
      id="subtitle"
      type="text"
      placeholder="Type a Subtitle"
      class="h-12 px-4 outline-none bg-gray-50 focus:bg-gray-100 rounded-md"
      bind:value={subtitle}
    />
  </div>

  <div class="flex items-center flex-wrap gap-10">
    <div class="flex flex-col gap-2">
      <label for="background" class="font-bold w-full">Background</label>

      <input
        id="background"
        type="color"
        placeholder="Choose a Background"
        bind:value={background}
      />
    </div>

    <div class="flex flex-col gap-2">
      <label for="color" class="font-bold w-full">Text Color</label>

      <input
        id="color"
        type="color"
        placeholder="Choose a Color"
        bind:value={color}
      />
    </div>
  </div>

  <button
    type="submit"
    class="block bg-indigo-500 hover:bg-indigo-600 active:bg-indigo-700 focus-visible:ring ring-indigo-300 text-white text-sm md:text-base font-semibold text-center rounded-lg outline-none transition duration-100 px-8 py-4"
    >Generate Image</button
  >
</form>
