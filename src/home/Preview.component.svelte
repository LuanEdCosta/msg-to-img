<script lang="ts">
  export let title: string
  export let subtitle: string
  export let background: string
  export let color: string
</script>

<div
  id="preview"
  style:color
  style:background
  class="rounded-lg p-4 h-64 w-full text-white text-center flex flex-col items-center justify-center gap-2"
>
  <div class="text-2xl font-bold">{title}</div>
  <div class="text-lg opacity-90">{subtitle}</div>
</div>
