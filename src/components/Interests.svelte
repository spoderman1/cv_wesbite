<script lang="ts">
    import { Carousel } from "flowbite-svelte";
    import Image_1 from "$lib/images/carousel/1.png";
    import Image_2 from "$lib/images/carousel/2.png";
    import Image_3 from "$lib/images/carousel/3.png";

    const images = [
        {
            alt: 'Starry night',
            src: Image_1,
            title: 'Starry night'
        },
        {
            alt: 'Japanese Turtle',
            src: Image_2,
            title: 'Japanese Turtle'
        },
        {
            alt: 'Coffee Cat',
            src: Image_3,
            title: 'Coffee cat'
        },
    ]
    const interests = {
        ai: "I've taken up interest in Generative AI and prompt engineering. I've always had an interest in art and creativity but lacked the skill to create and bring my imagination to life. I've created the above pieces and hundreds more with the use of prompt engineering and models such as Stable Diffusion",
    };
    let index = 0;
  let forward = true;
</script>

<div class="container">
    <h1 class="main-heading">Interests</h1>
    <div class="carousel-container">
    <Carousel {images} {forward} let:Indicators let:Controls bind:index>
      <Controls />
      <Indicators />
    </Carousel>
    </div>
    <div class="text-interests">
        <p class="mb-4 text-white text-base font-customMono text-gray-500 dark:text-gray-400">{interests.ai}</p>
    </div>
</div>


<style>
    .container {
        justify-content: center;
        width: 90%;
        margin-bottom: 10%;
    }
    .carousel-container {
        justify-content: center;
        width: 90%;
        margin-left: 10%;
    }
    .main-heading {
        font-family: 'Courier New', Courier, monospace;
        color: white;
        font-size: 3em;
        align-self: right;
        margin-left: 2%;
    }
    .text-interests {
        width: 90%;
        margin-top: 2%;
        margin-left: 2%;
    }
</style>