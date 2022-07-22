<script>
	export let name = 'John Doe'
	const logoName = name.match(/\b(\w)/g).join('');
</script>

<div class="person">
      <div class="mic"><span class="fas fa-microphone-slash"></span></div>
      <div class="symbol">{logoName}</div>
      <div class="name">{name}</div>
    </div>

<style>
.person {
  background: #3b4045;
  border-radius: 8px;
  width: 200px;
  height: 150px;
  padding: 2px;
  margin: 4px;
}
	.symbol {
  font-size: 46px;
  text-align: center;
  background: #e1546b;
  color: white;
  height: 60px;
  width: 60px;
  position: relative;
  left: 65px;
  top: 12px;
  border-radius: 50%;
  padding: 9px;
}

.name {
  position: relative;
  bottom: -25px;
  left: 10px;
  padding: 2px;
  font-size: 15px;
}

.mic {
  text-align: center;
  border-radius: 50%;
  height: 15px;
  width: 15px;
  background: #202124;
  font-size: 12px;
  padding: 4px;
  position: relative;
  top: 2px;
  left: 174px;
}
	


</style>