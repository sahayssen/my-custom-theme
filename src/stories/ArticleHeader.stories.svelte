<!--
  ArticleHeader.stories.svelte

  Stories for the ArticleHeader component.
  ArticleHeader renders the article headline plus optional byline/date metadata.

  Props:
  - headline: Main article headline text (required)
  - byline: Author name(s)
  - pubDate: Publication date in YYYY-MM-DD format
-->
<script module>
  import { defineMeta } from '@storybook/addon-svelte-csf';
  import ArticleHeader from '$lib/components/ArticleHeader.svelte';

  const { Story } = defineMeta({
    title: 'Components/ArticleHeader',
    component: ArticleHeader,
    tags: ['autodocs'],
    parameters: {
      // Keep a realistic reading-column width around the header preview.
      layout: 'fullscreen',
    },
    argTypes: {
      headline: {
        control: 'text',
        description: 'Primary article headline',
      },
      byline: {
        control: 'text',
        description: 'Author byline text',
      },
      pubDate: {
        control: 'text',
        description: 'Publication date in YYYY-MM-DD format',
      },
    },
  });
</script>

<Story
  name="Default"
  args={{
    headline: 'How Emma Lazarus Gave Voice to the Statue of Liberty',
    byline: 'Sarah Chen and Michael Rivera',
    pubDate: '1883-11-02',
  }}
>
  {#snippet children(args)}
    <div class="story-container">
      <ArticleHeader {...args} />
    </div>
  {/snippet}
</Story>

<Story
  name="Headline Only"
  args={{
    headline: 'The New Colossus at 140: Why the Poem Still Matters',
    byline: '',
    pubDate: '',
  }}
>
  {#snippet children(args)}
    <div class="story-container">
      <ArticleHeader {...args} />
    </div>
  {/snippet}
</Story>

<Story
  name="Byline Without Date"
  args={{
    headline: 'Inside the 354-Step Climb to the Statue Crown',
    byline: 'NYCity Data Desk',
    pubDate: '',
  }}
>
  {#snippet children(args)}
    <div class="story-container">
      <ArticleHeader {...args} />
    </div>
  {/snippet}
</Story>

<style>
  .story-container {
    width: 100%;
    max-width: var(--max-width);
    margin: 0 auto;
    padding: var(--spacing-lg) var(--spacing-md);
  }
</style>
