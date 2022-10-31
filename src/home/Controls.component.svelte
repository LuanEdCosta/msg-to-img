<script lang="ts">
  export let canCopyImage: boolean
  export let handleCopyImage: () => Promise<void>
  export let handleDiscardImage: () => void
</script>

<div class="flex items-center self-start gap-4">
  {#if canCopyImage}
    <button
      class="block border border-indigo-500 hover:border-indigo-600 text-indigo-500 hover:text-indigo-600 ring-indigo-300 focus-visible:ring text-sm md:text-base font-semibold text-center rounded-lg outline-none transition duration-100 px-6 py-2"
      on:click={handleCopyImage}>Copy Image</button
    >
  {/if}

  <button
    class="block border border-red-500 hover:border-red-600 text-red-500 hover:text-red-600 ring-red-300 focus-visible:ring text-sm md:text-base font-semibold text-center rounded-lg outline-none transition duration-100 px-6 py-2"
    on:click={handleDiscardImage}>Discard Image</button
  >
</div>
