<!--
@component
RelatedLinks.svelte — NYCity News Service Style Related Stories

Displays a "Related Stories" or "Recent News" section at the bottom
of articles with blue accent heading style.

USAGE EXAMPLE:
<RelatedLinks
  title="RELATED STORIES"
  links={[
    { headline: 'Mayor Announces New Transit Plan', href: '/transit-plan' },
    { headline: 'Budget Talks Continue Downtown', href: '/budget-talks' }
  ]}
/>
-->
<script>
  let {
    title = 'RELATED STORIES',
    links = [],
  } = $props();
</script>

{#if links.length > 0}
  <aside class="related-links" aria-labelledby="related-title">
    <h2 id="related-title" class="related-title">
      <span class="title-text">{title}</span>
    </h2>
  <div class="boxy">
    <ul class="link-list">
      {#each links as link (link.href)}
        <li class="link-item">
          <a href={link.href} class="link">
            {link.headline}
          </a>
        </li>
      {/each}
    </ul>
    
  </aside>
{/if}


<style lang="scss">
  @use '../styles' as *;

  .boxy{
    display: block;
    background-color: var(--color-dark); 
    padding: var(--spacing-md);
  }

  .related-links {
    margin-top: var(--spacing-xxl);
  }

  .related-title {
    display: block;
    align-items: center; 
    font-family: var(--font-menu);
    font-size: var(--font-size-lg);
    font-weight: var(--font-weight-bold);
    text-transform: uppercase;
    letter-spacing: var(--letter-spacing-wider);
    color: var(--color-dark);
    background-color: var(--color-btn-color);
    padding: var(--spacing-md);
    margin-bottom: 0;
  }

  .link-list {
    list-style: none;
    margin: var(--spacing-sm);
    padding: 0;
  }

  .link-item {
    margin-bottom: var(--spacing-md);
    padding-bottom: var(--spacing-md);
    border-bottom: var(--border-width-thin) solid var(--color-border);

    &:last-child {
      margin-bottom: 0;
      padding-bottom: 0;
      border-bottom: none;
    }
  }

  .link {
    font-family: var(--font-menu);
    font-size: var(--font-size-md); // Mobile-first: smaller size
    font-weight: var(--font-weight-normal);
    color: var(--color-accent);
    text-decoration: wavy;
    line-height: var(--leading-snug);
    display: block;
    transition: var(--transition-color);

    &:hover {
      color: var( --color-white);
      text-decoration: wavy;
    }

    @include tablet {
      font-size: var(--font-size-xl); // Larger screens: bigger size
    }
  }
</style>
