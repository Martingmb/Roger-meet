<script>
  import { fade } from "svelte/transition";
  import { LottiePlayer } from "@lottiefiles/svelte-lottie-player";
  import { onMount } from "svelte";
  let controlsLayout = [
    "previousFrame",
    "playpause",
    "stop",
    "nextFrame",
    "progress",
    "frame",
    "loop",
    "spacer",
    "background",
    "snapshot",
    "zoom",
    "info",
  ];

  let showOverlay = false;
  let toggleTransparency = false;
  const timerEnd = () => {
    showOverlay = true;
    toggleTransparency = true;
  };

  onMount(() => {
    setTimeout(timerEnd, 5000);
  });
</script>

<div class="logo" class:transparency={toggleTransparency} >
  <LottiePlayer
    src="https://assets7.lottiefiles.com/private_files/lf30_rjuv1b.json"
    autoplay={true}
    loop={true}
    controls={false}
    renderer="svg"
    background="transparent"
    height={20}
    width={1000}
    {controlsLayout}
  />
</div>
{#if showOverlay}  
<div class="overlay" transition:fade>
  <h1 class="message"><span>Happy </span>Last day!</h1>
  <p class="message">
    A un individuo increible con grandes ideas, trabajado y amable.
  </p>
  <p class="message">
    Fue un placer conocerte y trabajar contigo, espero tengas mucho exito en el
    futuro.
  </p>
  <p class="message">We are going to miss you!</p>
  <p class="message">-MG</p>
</div>
{/if}

<style>
  .message {
    color: white;
  }
  .logo {
    margin: auto;
    text-transform: uppercase;
    z-index: 1;
  }

  .transparency {
    opacity: 0.2;
  }

  .overlay {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    z-index: 2;
    height: 800px;
  }
</style>
