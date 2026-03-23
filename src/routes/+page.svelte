<!--
@component
This is your page!
-->
<script>
  // Import all the news furniture components
  import ArticleHeader from '$lib/components/ArticleHeader.svelte';
  import ArticleBody from '$lib/components/ArticleBody.svelte';
  import Image from '$lib/components/Image.svelte';
  import RelatedLinks from '$lib/components/RelatedLinks.svelte';
  import SplashHeader from '$lib/components/SplashHeader.svelte';

  // Article metadata
  let headline = 'Become a force for good. Join our next class.';
  let byline = 'NYCity News Service';
  let pubDate = '2026-01-31';

  // Related stories
  const relatedStories = [
    { headline: 'How America\'s top news organizations escape rigid publishing systems to design beautiful data-driven stories on deadline.', href: 'https://palewi.re/docs/coding-the-news/' },
    { headline: 'How to install, configure and use Visual Studio Code, GitHub and Copilot', href: 'https://palewi.re/docs/coding-the-news/scripts/week-1/' },
    { headline: "How to publish a website with Node.JS and GitHub Actions", href:"https://palewi.re/docs/coding-the-news/scripts/week-2/"},
  ];
</script>

<!-- This sets the page title in the browser tab -->
<svelte:head>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Caprasimo&display=swap" rel="stylesheet">
  <title>{headline} | NYCity News Service</title>
  <meta name="description" content="At the Craig Newmark Graduate School of Journalism at the City University of New York, change is in our DNA. That comes of being born in 2006, as the digital revolution was transforming our profession in ways none of us could have imagined." />
</svelte:head>

<!-- Your page content goes here -->
<div class="story-theme">
  <!-- Lead Image: Animated gif of students at the journalism school -->
  <Image
    src="/banner.jpg"
    alt="The Craig Newmark Graduate School of Journalism is at 219 West 40th Street in Midtown Manhattan."
  />
  <!-- Article Header: Headline, byline, and publication date -->
<SplashHeader
  kicker="Sophie's Website"
  headline="Sophie's First Header"
  deck="This is a custom header made by Sophie Hayssen for her Coding the News class"
  pubDate="March 18, 2026"
/> 

  
<div class="container">
  <!-- Article Body: The main story text with proper typography -->
  <ArticleBody>
    <p>
      At the Craig Newmark Graduate School of Journalism at the City University of New York, change is in our DNA. That comes of being born in 2006, as the digital revolution was transforming our profession in ways none of us could have imagined.
    </p>

    <p>
      We fashioned a school to teach the latest storytelling, entrepreneurial, and technological skills alongside reporting, writing, and ethics. Beyond that, we’ve crafted a culture that spurns complacency, that isn’t afraid to pivot before the ground under us shifts.
    </p>

    <p>
      Our mission is to serve the public interest – by training new journalists from varied economic, racial, and cultural backgrounds who will bring much-needed diversity to newsrooms, by helping mid-career journalists retool their skills, and by partnering with other media organizations to find new paths to excellence.
    </p>

    <p>
      Our low tuition rates, along with the added backing of private donors, allow candidates for our master’s degrees in journalism and engagement journalism to receive a world-class education at an affordable price. We also offer a unique bilingual master’s in journalism for students fluent in English and Spanish.
    </p>

    <p>
      Our three media centers provide research, training, thought leadership, industry meet-ups, and financial support for quality journalistic work.
    </p>

    <p>
      We also offer a robust professional education program through regular evening and weekend workshops. And we support in-depth reporting projects of professional journalists through fellowship grants.
    </p>

    <p>
      Classes are led by accomplished full-time faculty and adjuncts, who tap their networks to help students and graduates find internships, freelance opportunities and — the ultimate prize — jobs.
    </p>

    <p>
      At a time when our profession is reeling from financial pressures and lack of trust, the Newmark Graduate School of Journalism is committed to producing the next generation of skilled, ethically minded, and diverse journalists.
    </p>

    <p>
      We invite you to be part of our world.
    </p>
  </ArticleBody>

  <!-- Related Stories: Links to other articles -->
  <RelatedLinks
    title="Related Stories"
    links={relatedStories}
  />
</div>
</div>

<style lang="scss">
  @use '$lib/styles' as *;

  :global(.story-theme) {
    --color-background: #e0e0d6;
    --color-accent:  #d4e07d;
    --color-border:  #e0e0d6;

    @include mobile {
      .story-header h1 {
        font-size: var(--font-size-3xl);
      }


      .deck {
        font-size: var(--font-size-lg);
      }
    }
}
</style>