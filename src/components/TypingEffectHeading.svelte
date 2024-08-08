<script>
    import { fly } from 'svelte/transition';
    import { onMount } from 'svelte';
    import { Blockquote } from 'flowbite-svelte';
    import { QuoteSolid } from 'flowbite-svelte-icons';
   
    export let words = ["I can do Frontend (kinda) and Backend! APIs, and Mobile Dev are a breeze! I am a Full-Stack Engineer"];
    let currentWordIndex = 0;
    let currentWord = '';
    let isWiping = false;
  
    const typeSpeed = 10;
    const wipeSpeed = 50;
  
    onMount(() => {
      typeWord();
    });
  
    
    /**
   * @param {number | undefined} ms
   */
    function sleep(ms) {
    return new Promise(resolve => setTimeout(resolve, ms));
    }

    function typeWord() {
      let letters = words[currentWordIndex].split('');
      let index = 0;
      let typeInterval = setInterval(() => {
        if(index < letters.length) {
          currentWord = currentWord + letters[index];
          index++;
        } else {
          clearInterval(typeInterval);
          }
        }, 50);
    }
  
    function wipeWord() {
    sleep(1000);
      let letters = currentWord.split('');
      let index = letters.length - 1;
      let wipeInterval = setInterval(() => {
        if(index > -1) {
          currentWord = letters.slice(0, index).join('');
          index--;
        } else {
          clearInterval(wipeInterval);
          isWiping = false;
          currentWordIndex = (currentWordIndex + 1) % words.length;
          setTimeout(() => {
            typeWord();
          }, 1000);
        }
      }, 50);
     
    }
  </script>
  
  <style>
    .word {
      display: inline-block;
      font-size: 2rem;
      color: black;
      font-family: 'Courier New', Courier, monospace; 
      min-height: 30%;
    }
  </style>
  
  
  <span class="word" transition:fly={{ y: 100, duration: 5000 }}>
      <Blockquote class="p-4 my-4 text-white">
        {currentWord}
      </Blockquote>
  </span>