<script>
// @ts-nocheck

  import { onMount } from "svelte";

    export let width = 400;
    export let height = 400;
    export let background = 'black';
    export let color = 'white';

    let canvas;
    let context;
    let isDrawing;
    let start;

    onMount(() => {
        context = canvas.getContext('2d');
        context.lineWidth = 3;
        context.strokeStyle = color;
        //handleSize();
    })

    $: if(context) {
        context.strokeStyle = color;
    }

    export function handleStart ({ offsetX: x, offsetY: y})  {
        start = { x, y };
        isDrawing = true;        
        console.log('test2');
    }

    export function handleMove ({ offsetX: x1, offsetY: y1}) {
        //if(!isDrawing) return;

        const { x, y } = start;
        console.log({x, y});
        context.beginPath();
        context.moveTo(x, y);
        context.lineTo(x1, y1);
        console.log({x1, y1});
        context.closePath();
        context.stroke();
        console.log('test3');
        start = { x: x1, y: y1 };
    }

    export function handleEnd() { 
        isDrawing = false;
    }

</script>

<canvas 
    {width}
    {height}
    style:background={background}
    bind:this={canvas}
/>