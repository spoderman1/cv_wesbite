<script>
// @ts-nocheck

    import animation from "$lib/animations/programming.json";
    import Versofy_home_2 from "$lib/images/versofy_2.jpg";
    import Versofy_home from "$lib/images/versofy_home.webp";
    import { Button, Heading, Timeline, TimelineItem } from 'flowbite-svelte';
    import lottie from 'lottie-web';
    import { onMount } from 'svelte';
    import Keyword from "../components/Keyword.svelte";
    import Terminal from "../components/Terminal.svelte";
    import TypingEffectHeading from "../components/TypingEffectHeading.svelte";
    import Loom from "../lib/images/loom.jpg";
    import Loom_2 from "../lib/images/loom2.png";
    import Canvas from "../components/Canvas.svelte";
    import WholeTimeline from "../components/WholeTimeline.svelte";
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

<div class="container-profile">
    <div class="text-column">
        <h1 class='main-heading'>Hi, I'm Talha</h1>
    </div>
    <div class="image-column">
        <div class="image-box-animation">
            <div bind:this={animationContainer}></div>
        </div>
        <div class="image-box-profile">
               
        </div>
    </div>
</div>
<hr>
<div class="about-me">
    <div class="about-me-heading">
        <Heading tag="h1" class="mb-4" customSize="text-4xl font-customMono md:text-5xl lg:text-6xl">About Me</Heading>
    </div>
    <Terminal/>
</div>
<hr>
<div class="experience-container">
    <div class="experience-heading">
        <Heading tag="h1" class="mb-4 text-white" customSize="text-4xl font-customMono  md:text-5xl lg:text-6xl">My Experience</Heading>
    </div>
    <WholeTimeline/>
</div>
<hr/>
<div class="education-container">
    <div class="left-content">
        <Heading tag="h1" class="mb-4 text-white" customSize="text-4xl font-customMono  md:text-5xl lg:text-6xl">Education</Heading>
        <Heading tag="h1" class="mb-4 text-white" customSize="text-1xl font-customMono  md:text-2xl lg:text-2xl">Masters in Computer Science</Heading>
        <p class="mb-4 text-white">01/01/2024 - 01/12/2025</p>
        <p class="mb-4 text-white">I'm currently pursuing my masters by Research in the field of Computer Science, specifically in Probabilistic Modelling and AI in multi agent systems to determine outcomes.</p>
        <br/>
        <Heading tag="h1" class="mb-4 text-white" customSize="text-1xl font-customMono  md:text-2xl lg:text-2xl">Bachelors in Science in Information and Electrical Engineering</Heading>
        <p class="mb-4 text-white">01/01/2017 - 01/12/2018</p>
        <p class="mb-4 text-white">I completed my electrical engineering degree, with a greater emphasis on software, fundamentals of communications, networking, and design</p>
        <br/>
        <Heading tag="h1" class="mb-4 text-white" customSize="text-1xl font-customMono  md:text-2xl lg:text-2xl">Bachelors in Engineering Science in Biomedical Electrical Engineering</Heading>
        <p class="mb-4 text-white">01/01/2012 - 01/12/2016</p>
        <p class="mb-4 text-white">I completed my degree in Biomedical Engineering, the degree gave me a foundation in both medicine and electrical engineering with subjects like electronics, microprocessors, anatomy, and physiology</p>
    </div>
    <div class="right-content">
    </div>
</div>



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
            margin: 20 auto;
            padding-left: 50px;
            padding-bottom: 20px;
    }
    .text-column {
        flex: 1;
        padding-right: 20px;
    }

    .btn-contact-me {
        align-self: center;
        margin-top: 20px;
        font-family: 'Courier New', Courier, monospace;
    }

    .image-column {
        flex: 1;
        padding-left: 20px;
        gap: 20px;
        flex-direction:column;
    }
    .image-box-profile {
        flex: 1;
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

    hr {
        height: 1px;
        background-color: cadetblue;
        width: 60%;
        margin: 0 auto;
    }

    .experience-container {
        width: 80%;
        margin: 30px;
        justify-content: flex-start;
    }

    .experience-heading {
        align-items: "right";
        margin-bottom: 40px;
        font-family: 'Courier New', Courier, monospace; 
    }

    .timeline-container {
        margin: 20px;
        color: white;
    }

    .keywords-container {
        display: flex;
        flex-direction: row;
        justify-content: flex-start;
    }

    .timeline-screenshots-container {
        display: flex;
        flex-direction: row;
    }

    .timeline-screenshots {
        display: flex;
        flex-direction: row;
        margin: 20px;
        width: 10em;
        height: auto;
        justify-content: space-between;
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
        width: 100vw;
        box-sizing: border-box;
        padding: 20px;
    }

    .left-content {
  flex: 1;
  padding: 20px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: flex-start;
}

.left-content h1 {
  margin: 0;
  font-size: 2.5rem;
}

.left-content h2 {
  margin-top: 10px;
  font-size: 1.5rem;
}

.left-content p {
  margin-top: 20px;
  font-size: 1rem;
  line-height: 1.5;
}

.right-content {
  flex: 1;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 20px;
  box-sizing: border-box;
}
</style>