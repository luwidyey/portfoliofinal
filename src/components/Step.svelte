<script>
  export let step;
</script>

<div
  class="w-80 h-80 p-4 sm:p-6 md:p-8 flex flex-col gap-4 items-center justify-center rounded-lg border border-solid border-white text-center cursor-pointer group hover:border-red-400 duration-200"
>
  <h3 class="font-medium text-xl sm:text-2xl md:text-3xl">
    {step.name}
  </h3>
  <slot />
  <div>
    <a
      href={step.href}
      target="_blank"
      class="ml-auto cursor-pointer hover:text-slate-950 duration-200"
    >
      <p class="z-4">Go to &rarr;</p>
    </a>
  </div>
</div>
