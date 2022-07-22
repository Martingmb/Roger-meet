<script>
	import { createEventDispatcher } from 'svelte';
	export let meetName = 'Roger last daily';
	const time = new Date().toLocaleString('en-US', { hour: 'numeric', minute:'numeric', hour12: true })
	const dispatch = createEventDispatcher();
	
	const cameraOnClickHandler = (ev) => {
		dispatch('cameraClick', true)	
	}
	
</script>

<div class="bg-dark-gray footer">

    <div class="meeting-name">{meetName} | {time}</div>

    <div class="controls meeting-controls">
      <div class="bg-gray icon"><i class="fas fa-microphone"></i></div>
      <div class="bg-gray icon" on:click={cameraOnClickHandler}><i class="fas fa-video"></i></div>
      <div class="bg-gray icon"><i class="fas fa-closed-captioning"></i></div>
      <div class="bg-red icon"><i class="fa-solid fa-phone"></i></div>
    </div>

    <div class="controls meeting-chat">
      <div class="icon"><i class="fas fa-info"></i></div>
      <div class="icon"><i class="fa-solid fa-user-group"></i></div>
      <div class="icon"><i class="fas fa-message"></i></div>
      <div class="icon"><i class="fa-solid fa-shapes"></i></div>
    </div>

  </div>

<style>


.footer {
	flex-shrink: 0;
  display: flex;
  justify-content: space-between;
  padding: 10px;
  font-weight: bolder;
  align-items: center;
}

.controls {
  display: flex;
  flex-direction: row;
  justify-content: center;
  margin: 0 10px;
  flex-wrap: wrap;
}

.icon {
  width: 25px;
  height: 25px;
  border-radius: 50%;
  padding: 8px;
  margin: 0px 5px;
  font-size: 20px;
  flex-wrap: wrap;
  text-align: center;
  cursor: pointer;
}
	.icon:hover{
		background-color: white;
	}
	
.bg-gray {
  background: #3b4045;
}

.bg-dark-gray {
  background: #202124;
}

.bg-red {
  background: #cc0000;
}</style>