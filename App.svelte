<script>
	import Circle from "./Circle.svelte";
	import { onMount } from "svelte";

	const arr = Array.from(Array(50).keys());

	let counter = 0;
	onMount(() => {
	  const interval = setInterval(() => {
	    counter = counter + 1;
	  }, 5000);
	  return () => clearInterval(interval);
	});
</script>

<style>
  main {
    font-family: sans-serif;
    text-align: center;
    background: black;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    transform: rotate3d(1, 0, 10, var(--angle));
    transition: transform linear 10s;
  }
</style>

<svelte:head>
 <style>
   body {
    margin: 0;
    padding: 0;
    overflow: hidden;
    background: black;
    perspective: 800px;
  }
 </style>
</svelte:head>

<main style={`--angle: ${counter * 180}deg;`}>
	{#each arr as number}
    <Circle delay={number * 0.15} radius={50 * number} />
  {/each}
</main>