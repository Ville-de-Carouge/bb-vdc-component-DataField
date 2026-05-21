<script>
  import { getContext } from "svelte"

  export let datafield_name
  export let datafield_value
  export let datafield_name_color
  export let datafield_value_color
  export let font_size
  export let text_alignment
  

  const { styleable } = getContext("sdk")
  const component = getContext("component")
</script>

<div use:styleable={$component.styles}>
  <div class="container" style="--text-alignment:{text_alignment}">
    <p class="label-name" style="--size:{font_size-2}; --color:{datafield_name_color}">{datafield_name}</p>
    <p class="label-value" style="--size:{font_size}; --color:{datafield_value_color}">{datafield_value}</p>
  </div>
</div>

<style>
  .container {
    display: flex;
    flex-direction: column;
    align-items: var(--text-alignment);
  }

  p { 
    margin: 0; 
    font-family: "Source Sans 3", -apple-system, BlinkMacSystemFont, "Segoe UI", Inter, "Helvetica Neue", Arial, "Noto Sans", sans-serif; 
  }

  .label-name {
    color: var(--color);
    font-size: var(--size);
  }

  .label-value {
    color: var(--color);
    font-size: var(--size);
  }
</style>