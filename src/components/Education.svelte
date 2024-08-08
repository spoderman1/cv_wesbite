<script>
    import { AccordionItem, Accordion } from "flowbite-svelte";
    import GradIcon from "$lib/icons/Grad_Icon.svelte";
    let edu_masters = {
        header: "Masters in Computer Science",
        edu: "I'm currently pursuing my masters by Research in the field of Computer Science, specifically in Probabilistic Modelling and AI in multi agent systems to determine outcomes. The research aims to model possible behaviours of agents and the research is centered around trying to build tools and frameworks for Football coaches and analysts. The research can be extended to other scenarios where we have interactions between agents trying to achieve any particular goal",
        date: "01/01/2024 - 01/12/2025",
        icon: ""
    };
    let edu_elec = {
        header: "Bachelors in Science in Information and Electrical Engineering",
        edu: "I completed my electrical engineering degree, with a greater emphasis on software, fundamentals of communications, networking, and design. This degree primarily gave me the tools to be able to think outside the box and solve any problem given a goal and a set of constraints. I've understood the process to research, design, and iterate to build something of value",
        date: "01/01/2017 - 01/12/2018",
        icon: ""
    }
    let edu_biomed = {
        header: "Bachelors in Engineering Science in Biomedical Electrical Engineering",
        edu: "I completed my degree in Biomedical Engineering, the degree gave me a foundation in both medicine and electrical engineering with subjects like electronics, microprocessors, anatomy, and physiology. This degree gave me lots of exposure in both engineering and medical fields. While not directly used, the learning of anatomy and physiology gave me an appreciation and an interesting perspective in how systems are designed maintained",
        date: "01/01/2012 - 01/12/2016",
        icon: ""
    }
</script>

<div class="edu-container">
<Accordion flush>
    <AccordionItem>
        <span slot="header" class="text-base flex gap-2 text-white">
            <GradIcon class="w-6 h-6"/>
            <span>{edu_masters.header}</span>
        </span>
        <p class="mb-2 text-white">{edu_masters.edu}</p>
    </AccordionItem>
    <AccordionItem>
        <span slot="header" class="text-base flex gap-2 text-white">
            <GradIcon class="w-6 h-6"/>
            <span>{edu_elec.header}</span>
        </span>
        <p class="mb-2 text-white dark:text-gray-400">{edu_elec.edu}</p>
    </AccordionItem>
    <AccordionItem>
        <span slot="header" class="text-base flex gap-2 text-white">
            <GradIcon class="w-6 h-6"/>
            <span>{edu_masters.header}</span>
        </span>
        <p class="mb-2 text-white dark:text-gray-400">{edu_biomed.edu}</p>
    </AccordionItem>
</Accordion>
</div>


<style>
    .edu-container {
        width: 90%;
        align-items: "center";
        margin: 10px;
    }
</style>