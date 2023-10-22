<script>
	import Circle from "../lib/Circle.svelte";

	const arr = Array.from(Array(50).keys());
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

<main>
	{#each arr as number}
    <Circle delay={number * 0.15} radius={50 * number} />
  {/each}
</main>