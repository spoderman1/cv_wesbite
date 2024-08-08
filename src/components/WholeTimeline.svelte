<script>
    import Keyword from './Keyword.svelte';
    import { Timeline, TimelineItem, Heading } from 'flowbite-svelte';
    let versofy = {
        title: 'Versofy Solar',
        experience: "I worked as a Full Stack Engineer on their React Native app. The app was written in TypeScript. The backend was built on Serverless Framework using TypeScript and was hosted on AWS. I worked on all aspects of the stack, from design and execution of Frontend elements, to databases and api's on the backend. A FullStack feature I worked intensively on is the Timeline Feature",
        date: "November 2023 - September 2024"
    }
    let iress = {
        title: 'Iress',
        experience: "I worked in an agile team delivering and improving on fintech systems. I worked on a Node application that created and handled financial information such as stock prices through the use of web urls and GraphQL. Built an API in NodeJs that returned company ESG data. The data was populated via a scheduled AWS Lambda that accessed an FTP server, downloaded data, and populated our database. I also worked on new DevOps pipelines by migrating old infrastructure onto new servers.",
        date: "September 2021 - August 2023"
    }
    let kopano = {
        title: 'Kopano Ai',
        experience: "I worked as a Full Stack Engineer on their React website, and their ASP.NET Web API backend. I built entire systems of business logic such as the Claims process and gained valuable experience in designing and implementing full stack tasks",
        date: "November 2018 - September 2021"
    }
</script>

<Timeline order="vertical">
    <TimelineItem>
        <Heading tag="h1" class="mb-4 text-white" customSize="text-2xl font-customMono md:text-2xl lg:text-2xl">{versofy.title}</Heading>
        <Heading tag="h1" class="mb-4 text-white" customSize="text-1xl font-customMono md:text-1xl lg:text-1xl">{versofy.date}</Heading>
        <p class="mb-4 text-white text-base font-customMono text-gray-500 dark:text-gray-400">{versofy.experience}</p>
        <div class="keywords-container">
            <Keyword description="React Native" icon="react"/>
            <Keyword description="TypeScript" icon="typescript"/>
            <Keyword description="Serverless" icon="serverless"/>
            <Keyword description="AWS" icon="aws"/>
        </div>
    </TimelineItem>
    <TimelineItem>
        <Heading tag="h1" class="mb-4 text-white" customSize="text-2xl font-customMono md:text-2xl lg:text-2xl">{iress.title}</Heading>
        <Heading tag="h1" class="mb-4 text-white" customSize="text-1xl font-customMono md:text-1xl lg:text-1xl">{iress.date}</Heading>
        <p class="mb-4 text-white text-base font-customMono text-gray-500 dark:text-gray-400">{iress.experience}</p>
        <div class="keywords-container">
            <Keyword description="NodeJs" icon="node"/>
            <Keyword description="Terraform" icon="terraform"/>
            <Keyword description="AWS Lambda" icon="lambda"/>
        </div>
    </TimelineItem>
    <TimelineItem>
        <Heading tag="h1" class="mb-4 text-white" customSize="text-2xl font-customMono md:text-2xl lg:text-2xl">{kopano.title}</Heading>
        <Heading tag="h1" class="mb-4 text-white" customSize="text-1xl font-customMono md:text-1xl lg:text-1xl">{kopano.date}</Heading>
        <p class="mb-4 text-white text-base font-customMono text-gray-500 dark:text-gray-400">{kopano.experience}</p>
        <div class="keywords-container">
            <Keyword description="React" icon="react"/>
            <Keyword description="ASP.Net" icon="asp"/>
            <Keyword description="AWS" icon="aws"/>
        </div>
    </TimelineItem>
</Timeline>


<style>
    .timeline-container {
        margin: 20px;
        color: white;
    }

    .keywords-container {
        display: flex;
        flex-direction: row;
        justify-content: flex-start;
    }
</style>
  
