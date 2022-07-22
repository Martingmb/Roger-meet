<script>
	import { fade } from 'svelte/transition';
	import { createEventDispatcher } from 'svelte';
	import Participant from './participant.svelte'
	import Footer from './footer.svelte'
	const meetName = 'Roger last daily'
	const time = new Date().toLocaleString('en-US', { hour: 'numeric', minute:'numeric', hour12: true })
	const dispatch = createEventDispatcher();
	function cb(event) {
		dispatch('cameraClick', true)	
	}
</script>

<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" integrity="sha512-9usAa10IRO0HhonpyAIVpjrylPvoDwiPUiKdWk5t3PyolY1cOd4DSE0Ga+ri4AuTroPR5aQvXU9xC6qOPnzFeg==" crossorigin="anonymous" referrerpolicy="no-referrer" />

  <div class="container" transition:fade>
    <Participant name='Roger Fernandez'/>
		<Footer on:cameraClick={cb}/>
  </div>

<style>
	:global(body) {
  background: #202124;
  color: #ccc;
  font-family: sans-serif;
}

.container {
  display: flex;
	height: 100%;
    padding: 0;
    margin: 0;
  flex-direction: column;
  display: flex;
    align-items: center;
    justify-content: center;
}
</style>