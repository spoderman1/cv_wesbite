<script>
// @ts-nocheck

    import animation from "$lib/animations/programming.json";
    import { Button, Heading, Timeline, TimelineItem, Hr } from 'flowbite-svelte';
    import { QuoteSolid } from 'flowbite-svelte-icons';
    import lottie from 'lottie-web';
    import { onMount } from 'svelte';
    import Keyword from "../components/Keyword.svelte";
    import Terminal from "../components/Terminal.svelte";
    import TypingEffectHeading from "../components/TypingEffectHeading.svelte";
    import WholeTimeline from "../components/WholeTimeline.svelte";
    import Education from "../components/Education.svelte";
    import Profile from "../lib/images/pic.png";
    import Interests from "../components/Interests.svelte";
    import Footer from "../components/Footer.svelte";
    /**
   * @type {HTMLDivElement}
   */
    let animationContainer;
    let drawingCanvas;

    onMount(() => {
        lottie.loadAnimation({
            container: animationContainer,
            renderer: 'svg',
            loop: true,
            autoplay: true,
            animationData: animation
        });
        createStars();
    });

    function createStars() {
    const numberOfStars = 100;
    const starContainer = starsContainer;

    for (let i = 0; i < numberOfStars; i++) {
      const star = document.createElement("div");
      star.classList.add("star");
      const { x, y } = getRandomPosition();
      star.style.top = `${y}%`;
      star.style.left = `${x}%`;
      starContainer.appendChild(star);
    }
  }

  function getRandomPosition() {
    const x = Math.random() * 100;
    const y = Math.random() * 100;
    return { x, y };
  }

    let starsContainer;
    let stars = [
    { top: '10%', left: '20%', size: '3px', duration: '2s' },
    { top: '15%', left: '80%', size: '2px', duration: '3s' },
    { top: '30%', left: '50%', size: '4px', duration: '2.5s' },
    { top: '45%', left: '10%', size: '2px', duration: '1.8s' },
    { top: '60%', left: '70%', size: '3px', duration: '2.2s' },
    { top: '75%', left: '30%', size: '2px', duration: '2.7s' },
    { top: '85%', left: '90%', size: '3px', duration: '3.1s' },
    { top: '90%', left: '40%', size: '2px', duration: '2.4s' },
    { top: '25%', left: '60%', size: '3px', duration: '2s' },
    { top: '50%', left: '20%', size: '2px', duration: '1.5s' },
  ];

    function startAnimation() {
        console.log('test');
        drawingCanvas.handleStart({offsetX: 0, offsetY: 400});
        for (let i = 0; i < pathCoordinates.length - 1; i++) {
            const {x, y} = pathCoordinates[i];
            drawingCanvas.handleMove({offsetX: x, offsetY: y});
            setTimeout
        }
    }

    function stopAnimation() {
        drawingCanvas.handleEnd();
    }

</script>
<div bind:this={starsContainer} class="backdrop">
    {#each stars as star}
    <div class="star" style="top: {star.top}; left: {star.left}; width: {star.size}; height: {star.size}; animation-duration: {star.duration};">
    </div>
    {/each}
</div>
<div class="container-profile">
    <div class="text-column">
        <h1 class="main-heading">Hi, I'm Talha</h1>
        <TypingEffectHeading/>
        <div class="image-box-profile">
            <img src={Profile} alt="Profile Picture" width="200" height="200"/>
        </div>

    </div>
    <div class="image-column">
        <div class="image-box-animation">
            <div bind:this={animationContainer}></div>
        </div>
    </div>
</div>
<Hr classHr="my-8 w-64 h-1" icon>
    <QuoteSolid class="w-6 h-6 text-gray-700 dark:text-gray-300" />
</Hr>
<div class="about-me">
    <div class="about-me-heading">
        <h1 class="experience-heading" >About Me</h1>
    </div>
    <Terminal/>
</div>
<Hr classHr="my-8 w-64 h-1" icon>
    <QuoteSolid class="w-6 h-6 text-gray-700 dark:text-gray-300" />
  </Hr>
<div class="experience-container">
    <div class="experience-heading">
        <Heading tag="h1" class="mb-4 text-white" customSize="text-4xl font-customMono  md:text-5xl lg:text-6xl">My Experience</Heading>
    </div>
    <WholeTimeline/>
</div>

<Hr classHr="my-8 w-64 h-1" icon>
    <QuoteSolid class="w-6 h-6 text-gray-700 dark:text-gray-300" />
  </Hr>
<div class="education-container">
    <div class="experience-heading">Education</div>
    <Education/>
</div>
<Hr classHr="my-8 w-64 h-1" icon>
    <QuoteSolid class="w-6 h-6 text-gray-700 dark:text-gray-300" />
  </Hr>

<Interests/>
<Footer/>


<style>
    .main-heading {
        font-family: 'Courier New', Courier, monospace;
        color: white;
        font-size: 3em;
    }
    .backdrop {
        position: fixed;
        top: 0;
        left: 0;
        width: 100vw;
        height: 100vh;
        overflow: hidden;
        z-index: -1;
        background: black;
    }

    .star {
        position: absolute;
        width: 2px;
        height: 2px;
        background-color: white;
        border-radius: 50%;
        z-index: 2;
        box-shadow: 0 0 6px 2px rgba(255, 255, 255, 0.8);
        animation: twinkle 2s infinite ease-in-out alternate;
    } 
    .container-profile {
            display: flex;
            flex-direction: row;
            justify-content: space-between;
            align-items: center;
            margin-top: 50px;
            padding-left: 50px;
            padding-bottom: 20px;
    }
    .text-column {
        flex: 1;
        padding-right: 20px;
        margin-top: 20px;
    }

    .image-column {
        flex: 1;
        padding-left: 20px;
        gap: 20px;
        flex-direction:column;
    }
    .image-box-profile {
        flex: 2;
        display: flex;
        justify-content: center;
        align-items: center;
        margin-bottom: 10px;
    }
    .image-box-animation {
        flex: 1;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .experience-container {
        width: 80%;
        margin: 50px;
        justify-content: flex-start;
    }

    .experience-heading {
        align-items: "center";
        font-family: 'Courier New', Courier, monospace;
        font-size: 4em;
        color: white; 
        margin-bottom: 50px;
    }

    .about-me-heading {
        align-items: "right";
        margin-top: 40px;
        font-family: 'Courier New', Courier, monospace; 
        color: white;
    }

    .about-me {
        display: flex;
        flex-direction: column;
        margin: auto;
        align-items: center;
    }

    .education-container {
        display: flex;
        flex-direction: column;
        width: 100vw;
        box-sizing: border-box;
        padding: 20px;
    }
</style>