<script>
// @ts-nocheck
    import { onMount } from 'svelte';
    import aboutMe from "../lib/information/about-me";
    import TypingEffect from './TypingEffectTerminal.svelte';

    let typing_key = 0;
    let terminal;
    let terminal_content_style = {
        'font-family': '"Courier New", Courier, monospace', 
        'color': '#20C20E',
        'font-size': '0.9rem', 
        'line-height': '1.5',
    }
    $: terminal_content_label = 'Basic info';
    $: terminal_content = aboutMe.get(terminal_content_label);
    function refreshTyping() {
        typing_key++;
    }
</script>

<div bind:this={terminal} class="terminal">
    <h2 class="terminal-title">{terminal_content_label}</h2>
        <div class="terminal-description-container">
            <TypingEffect key={typing_key} words={terminal_content} style={terminal_content_style}/>
        </div>
</div>

<style>
    .terminal {
        display: flex;
        flex-direction: column;
        justify-content: flex-start;
        align-items: flex-start;
        padding: 20px;
        margin: 20px;
        border-radius: 10px;
        background-color: black;
        border-color: white;
        border-width: 2px;
        box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        transition: all 0.3s ease;
        width: 80%;
    }

    .terminal-title {
        font-size: 1.5rem;
        font-weight: 700;
        color: white;
        align-items: flex-start;
        margin-bottom: 0.5rem;
        padding-left: 10px;
        font-family: 'Courier New', Courier, monospace; 
    }

    .terminal-description-container {
        background-color: black; /* Light grey background */
        padding: 1rem;            /* Padding around the text */
        border-radius: 10px;
        white-space: pre-wrap;    /* Preserve formatting like line breaks and spaces */
        border-width: 1px;
        width: 100%;
    }
</style>


