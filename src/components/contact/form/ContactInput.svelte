<script lang="ts">
  export let name: string;
  export let label: string;
  export let placeholder: string;
  export let type: string;
  export let value: string = "";
  export let error = "";

  const handleInput = (event: Event) => {
    const target = event.target as HTMLInputElement;
    value = target.value;
  };
</script>

<div>
  <div class="contact__form-div dark:!border-gray-400">
    <label class="contact__form-tag dark:!bg-[#13161d] text-xs " for={name}
      >{label}</label
    >
    <input
      {type}
      required
      class:error
      class="contact__form-input dark:border-gray-600"
      {placeholder}
      {name}
      on:input={handleInput}
      bind:value
    />
  </div>
  {#if error}
    <span class="block text-sm text-red-600 -mt-8 ml-2">{error}</span>
  {/if}
</div>
