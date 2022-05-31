<script context="module">
  import { tutorials } from "$lib/data/tutorials";
  
  export async function load({ page }) {
    console.log('CONSOLE', page, tutorials);
    let tutorial = tutorials.find(tut => tut.slug === page.params.slug)
    const url = `${tutorial.raw}`;
    const response = await fetch(url);

    return {
      status: response.status,
      props: {
        title: tutorial.title,
        article: response.ok && (await response.text())
      }
    };
  }
</script>

<script>
import Container from '$lib/components/atoms/Container.svelte';

  import SvelteMarkdown from 'svelte-markdown'


  export let article;
  export let title;

</script>

<Container>
  <SvelteMarkdown source={article} />

</Container>

