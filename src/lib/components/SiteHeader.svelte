<!--
@component
SiteHeader.svelte — NYCity News Service Style Header
-->
<script>
  let {
    navLinks = [],
  } = $props();
</script>

<header class="site-header">
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Caprasimo&family=Chicle&family=Roboto+Mono:ital,wght@0,100..700;1,100..700&family=Roboto+Slab:wght@100..900&family=Roboto:ital,wght@0,100..900;1,100..900&display=swap" rel="stylesheet">
  <div class="masthead-wrapper">
        <span class="logo-txt"> Sophie Hayssen </span>

    {#if navLinks.length > 0}
      <nav class="main-nav" aria-label="Main navigation">
        <ul class="nav-list">
          {#each navLinks as link}
            <li>
              <a href={link.href} class="nav-link">{link.label}</a>
            </li>
          {/each}
        </ul>
      </nav>
    {/if}
  </div>
</header>

<style lang="scss">
  @use '../styles' as *;


  .logo-txt {
    display: flex;
    font-family: "Chicle", serif;
    font-weight: 400;
    font-style: normal;
    color: var(--color-green-light);
    padding: 2.5rem;
  }
  .site-header {
    font-size: var(--font-size-6xl);
    display: block;
  }
  .masthead-wrapper {
    background: var(--color-darkgreen);
    background-size: 400% 200%;
    display: flex;
    justify-content: flex-start;
    gap: var(--spacing-xl);
    width: 100%;
  }

  /* Compact Masthead - Mobile: centered */
  .masthead {
    font-size: 4rem;
    align-items: center;
    justify-content: center;
  }

  .logo-text {
    font-size: 4rem;
    font-color:var(--color-green-light);
    font-family: "Caprasimo", serif;
    font-weight: 400;
    font-style: normal;
    display: flex;
}
  /* Navigation - hidden on mobile */
  .main-nav {
    display: none;
  }

  .nav-list {
    display: flex;
    flex-wrap: nowrap;
    list-style: none;
    gap: var(--spacing-sm);
  }

  .nav-link {
    display: flex;
    padding: var(--spacing-md);
    color: var(--color-green-light);
    text-decoration: none;
    font-family: var(--font-sans);
    font-size: var(--font-size-xs);
    font-weight: var(--font-weight-semibold);
    text-transform: uppercase;
    letter-spacing: var(--letter-spacing-wide);
    white-space: nowrap;
    transition: var(--transition-opacity);
    font-family: "Roboto Mono", monospace;
    font-optical-sizing: auto;
    font-style: normal;
    
  }

  .nav-link:hover {
    color: var(--color-btn-color);
    opacity: var(--opacity-hover);
    text-decoration: none;
  }

  /* Desktop styles - show nav, space-between layout, larger logo */
  @include desktop {
    .masthead {
      justify-content: space-between;
      padding: var(--font-size-xs) var(--spacing-md);
    }

    .logo-nycity {
      font-size: var(--font-size-base);
      padding: var(--logo-padding-desktop);
    }

    .logo-news-service {
      font-size: var(--font-size-base);
      padding: var(--logo-padding-desktop);
    } 

    .main-nav {
      display: flex;
      align-items: center;
    }
  }

</style>
