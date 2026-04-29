<script lang="ts">
  import type { Snippet } from 'svelte';

  let { href, children, class: className = '' } = $props<{
    href: string;
    children?: Snippet;
    class?: string;
  }>();
</script>

<a 
  {href} 
  class="text-h2 text-link-default hover:text-link-hover active:text-link-hover transition-colors py-1 whitespace-nowrap {className}"
>
  {@render children?.()}
</a>
