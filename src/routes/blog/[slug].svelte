<script context="module">
  export async function load(ctx) {
    let slug = ctx.page.params.slug;

    console.log('some', slug, ctx);
    const post = {
      name: 'Post 1',
      content: 'content',
    };
    return { props: { slug, post } }
  }

</script>

<script>
  export let slug;
  export let post;
</script>



<h1>{slug}</h1>
<h3>{post.name}</h3>