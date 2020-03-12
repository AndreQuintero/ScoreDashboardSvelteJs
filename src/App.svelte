<script>
	import Navbar from './Navbar.svelte';
	import Player from './Player.svelte';
	import AddPlayer from './AddPlayer.svelte';

	let players = [
		{
			name: "André",
			points: 100
		},
		{
			name: "Diego",
			points: 100
		}
	];

	const addPlayer = (e) => {
		const newPlayer = e.detail;
		players = [...players, newPlayer];

	};

	const removePlayer = (e) => {
		players = players.filter(player => player.name !== e.detail);
	}

</script>

<Navbar />
<div class="container">
	{#if players.length === 0}
		<p>No players</p>
	{:else} 
		{#each players as player}
			<Player name={player.name} points={player.points} on:removePlayer={removePlayer}/>
		{/each}	
	{/if}
	<AddPlayer on:addPlayer={addPlayer}/>
</div>

<style>
</style>