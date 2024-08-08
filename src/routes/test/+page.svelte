<script>
    import Keyword from '../../components/Keyword.svelte';
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


    <Timeline>
        <TimelineItem title={versofy.title} date={versofy.date}>
          <p class="mb-4 text-base font-normal text-gray-500 dark:text-gray-400">Get access to over 20+ pages including a dashboard layout, charts, kanban board, calendar, and pre-order E-commerce & Marketing pages.</p>
        </TimelineItem>
        <TimelineItem title={iress.title} date={iress.date}>
          <p class="text-base font-normal text-gray-500 dark:text-gray-400">All of the pages and components are first designed in Figma and we keep a parity between the two versions even as we update the project.</p>
        </TimelineItem>
        <TimelineItem title={kopano.title} date={kopano.date}>
          <p class="text-base font-normal text-gray-500 dark:text-gray-400">Get started with dozens of web components and interactive elements built on top of Tailwind CSS.</p>
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
  