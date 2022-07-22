<script>
	import Meet from './meetScreen.svelte'
	import Goodbye from './goodbye.svelte'
	let checkMeetState = false;
	const isMeetDone = (ev) => {
		if(ev.detail) {
			checkMeetState = true;
		}
	}
	
</script>

{#if checkMeetState}
<Goodbye/>
{:else}
<Meet on:cameraClick={isMeetDone}/>
{/if}
