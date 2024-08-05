<script>
    import { fly } from 'svelte/transition';
    import { afterUpdate, onDestroy, onMount } from 'svelte';
   
    export let words = 'Fast';
    let currentWordIndex = 0;
    let terminal_text_style = ""
    let currentWord = '';
    let isWiping = false;
    let animate = false;
    export let typing_key = 0;
  
    const typeSpeed = 25;
  
    onMount(() => {
        animate = true;
        typeWord();
    });

    function typeWord() {
      let letters = words.split('');
      let index = 0;
      let typeInterval = setInterval(() => {
        if(index < letters.length) {
          currentWord = currentWord + letters[index];
          index++;
        } else {
          clearInterval(typeInterval);
          }
        }, typeSpeed);
    }
  
  
    function typeWordAndWipe() {
      let letters = words[currentWordIndex].split('');
      let index = 0;
      let typeInterval = setInterval(() => {
        if(index < letters.length) {
          currentWord = currentWord + letters[index];
          index++;
        } else {
          clearInterval(typeInterval);
          setTimeout(() => {
            wipeWord();
          }, 1000);
          }
        }, 50);
    }
  
    function wipeWord() {
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
          }, 150);
        }
      }, 150);
     
    }
  </script>
  
  <style>
    .word {
      display: inline-block;
      font-size: 0.9rem;
      color: #20C20E;
      line-height: 1.5;
    }
  </style>
  
  
  <span class="word" transition:fly ={{ y: 100, duration: 5 }}>
      {currentWord}
  </span>