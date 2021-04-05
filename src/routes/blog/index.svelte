<h1>Blog page</h1>


<script>
  let response;

  try {
    response = fetch('https://bing-news-search1.p.rapidapi.com/news?safeSearch=Off&textFormat=Raw',
      {
        method: 'GET',
        headers: {
          'x-bingapis-sdk': 'true',
          'x-rapidapi-key': '3700d7e2a0mshf9e9fd678dd034bp109039jsna5b3901c047d',
          'x-rapidapi-host': 'bing-news-search1.p.rapidapi.com',
        },
      },
    ).then(data => data.json());
  } catch (error) {
    console.log(error);
  }
</script>

{#await response}
  <pre>
		Awaiting...
	</pre>
{:then result}
  <h2>OK</h2>
  {result.value.map(item => {
  return `<a href="/blog">${item.name}</a>`
  })}
{:catch error}
  <h2>Error</h2>
  <pre>
		{error.toString()}
	</pre>
{/await}
<a href="/blog/hello">Hello world</a>
<a href="/blog/learn-sveltekit">Svelte-kit</a>