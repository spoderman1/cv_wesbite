<script>
// @ts-nocheck

    import animation from "$lib/animations/programming.json";
    import profile_picture from "$lib/images/me.jpg";
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
    })

    const pathCoordinates = [
  { x: 50, y: 350 },  // Start
  { x: 70, y: 330 },
  { x: 90, y: 310 },
  { x: 110, y: 290 },  // Ascend to first plateau
  { x: 130, y: 290 },  // Plateau 1
  { x: 150, y: 270 },  // Descend from first plateau
  { x: 170, y: 260 },
  { x: 190, y: 250 },
  { x: 210, y: 240 },  // Ascend to second plateau
  { x: 230, y: 240 },  // Plateau 2
  { x: 250, y: 230 },  // Descend from second plateau
  { x: 270, y: 220 },
  { x: 290, y: 200 },
  { x: 310, y: 180 },
  { x: 330, y: 160 },  // Ascend to the peak
  { x: 350, y: 140 },
  { x: 370, y: 120 },  // Peak
];
const flagPositions = [
  { x: 120, y: 280 },
  { x: 240, y: 200 },
  { x: 380, y: 100 },
];
    let versofy = {
        title: "Versofy Solar",
        experience: "I worked as a Full Stack Engineer on their React Native app. The app was written in TypeScript. The backend was built on Serverless Framework using TypeScript and was hosted on AWS. I worked on all aspects of the stack, from design and execution of Frontend elements, to databases and api's on the backend. A FullStack feature I worked intensively on is the Timeline Feature"
    }
    let iress = {
        title: "Iress",
        experience: "I worked in an agile team delivering and improving on fintech systems. I worked on a Node application that created and handled financial information such as stock prices through the use of web urls and GraphQL. Built an API in NodeJs that returned company ESG data. The data was populated via a scheduled AWS Lambda that accessed an FTP server, downloaded data, and populated our database. I also worked on new DevOps pipelines by migrating old infrastructure onto new servers."
    }
    let kopano = {
        title: "Kopano ai",
        experience: "I worked as a Full Stack Engineer on their React website, and their ASP.NET Web API backend. I built entire systems of business logic such as the Claims process and gained valuable experience in designing and implementing full stack tasks"
    }

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

<span class="container-profile">
    <div class="text-column">
        <Heading tag="h1" class="mb-4" customSize="text-4xl font-customMono  md:text-5xl lg:text-6xl">Hi, I'm Talha</Heading>
        <TypingEffectHeading/>
        <div class="btn-contact-me">
        <Button href="/" color='dark'>Contact Me</Button>
        </div>  
    </div>
    <div class="image-column">
        <div class="image-box-profile">
            <img src={profile_picture} alt="Me"/>
        </div>
        <div class="image-box-animation">
            <div bind:this={animationContainer}></div>
        </div>
    </div>
</span>
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
     <Heading tag="h1" class="mb-4" customSize="text-4xl font-customMono  md:text-5xl lg:text-6xl">My Experience</Heading>
    </div>
</div>
<div class="timeline-container">
<Timeline order="vertical">
    <TimelineItem title={versofy.title} date="November 2023 - August 2024">
        <p class="mb-4 text-base font-customMono text-gray-500 dark:text-gray-400">{versofy.experience}</p>
        <div class="keywords-container">
            <Keyword description="React Native" icon="react"/>
            <Keyword description="TypeScript" icon="typescript"/>
            <Keyword description="Serverless" icon="serverless"/>
            <Keyword description="AWS" icon="aws"/>
        </div>
    <div class="timeline-screenshots-container">
            <div class="timeline-screenshots">
                <img src={Versofy_home} alt="Versofy Home Screen"/>
            </div>
            <div class="timeline-screenshots">
            <img src={Versofy_home_2} alt="Versofy Home Screen"/>
            </div>
    </div>
    </TimelineItem>
    <TimelineItem title={iress.title} date="September 2021 - August 2023">
        <p class="mb-4 text-base font-customMono text-gray-500 dark:text-gray-400">{iress.experience}</p>
        <div class="keywords-container">
            <Keyword description="NodeJs" icon="node"/>
            <Keyword description="Terraform" icon="terraform"/>
            <Keyword description="AWS Lambda" icon="lambda"/>
        </div>
    </TimelineItem>
    <TimelineItem title={kopano.title} date="November 2018 - September 2021">
        <p class="mb-4 text-base font-customMono text-gray-500 dark:text-gray-400">{kopano.experience}</p>
        <div class="keywords-container">
            <Keyword description="React" icon="react"/>
            <Keyword description="ASP.Net" icon="asp"/>
            <Keyword description="AWS" icon="aws"/>
        </div>
        <div class="timeline-screenshots-container">
            <div class="timeline-screenshots">
                <img src={Loom} alt="Versofy Home Screen"/>
            </div>
            <div class="timeline-screenshots">
            <img src={Loom_2} alt="Versofy Home Screen"/>
            </div>
    </div>
    </TimelineItem>
</Timeline>
</div>
<hr/>
<div class="education-container">
    <div class="left-content">
        <Heading tag="h1" class="mb-4" customSize="text-4xl font-customMono  md:text-5xl lg:text-6xl">Education</Heading>
        <Heading tag="h1" class="mb-4" customSize="text-1xl font-customMono  md:text-2xl lg:text-2xl">Masters in Computer Science</Heading>
        <p>01/01/2024 - 01/12/2025</p>
        <p>I'm currently pursuing my masters by Research in the field of Computer Science, specifically in Probabilistic Modelling and AI in multi agent systems to determine outcomes.</p>
        <br/>
        <Heading tag="h1" class="mb-4" customSize="text-1xl font-customMono  md:text-2xl lg:text-2xl">Bachelors in Science in Information and Electrical Engineering</Heading>
        <p>01/01/2017 - 01/12/2018</p>
        <p>I completed my electrical engineering degree, with a greater emphasis on software, fundamentals of communications, networking, and design</p>
        <br/>
        <Heading tag="h1" class="mb-4" customSize="text-1xl font-customMono  md:text-2xl lg:text-2xl">Bachelors in Engineering Science in Biomedical Electrical Engineering</Heading>
        <p>01/01/2012 - 01/12/2016</p>
        <p>I completed my degree in Biomedical Engineering, the degree gave me a foundation in both medicine and electrical engineering with subjects like electronics, microprocessors, anatomy, and physiology</p>
    </div>
    <div class="right-content">
        <Canvas bind:this={drawingCanvas} width={300}/>
        <div class="canvas-controls">
            <Button on:click={startAnimation} color="dark" pill>Play</Button>
            <Button on:click={stopAnimation} color="dark" pill>Stop</Button>
        </div>
    </div>
</div>


<style>
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
        height: 2px;
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

canvas {
  width: 100%;
  height: auto;
  max-width: 500px;
  max-height: 500px;
  border: 1px solid #000;
  background-color: #f5f5f5;
}

.canvas-controls {
    padding: 20px;
}



</style>