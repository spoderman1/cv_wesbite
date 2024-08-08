<script>
    import { Carousel, Thumbnails } from "flowbite-svelte";
    const images = [
        {
            alt: 'Samurai Cat',
            src: '../lib/images/carousel/1.png',
            title: 'samurai cat'
        },
    ]
    let index = 0;
  let forward = true;
</script>


<div class="max-w-4xl space-y-4">
    <Carousel {images} {forward} let:Indicators let:Controls bind:index>
      <Controls />
      <Indicators />
    </Carousel>
    <Thumbnails {images} {forward} bind:index />
</div>

<style>

</style>