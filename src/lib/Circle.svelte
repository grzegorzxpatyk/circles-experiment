<script>
export let delay = 2;
export let radius = 25;
</script>

<style>
  div {
    position: fixed;
    /* top: 75vh; */
    top: calc(5vw - (10px * var(--top)));
    transform: translate(-var(--radius), 0);
    background: none;
    border-radius: 50%;
    border: 1px solid var(--color);
    width: var(--radius);
    height: var(--radius);
    opacity: 0;
    animation: var(--duration) ease-in-out infinite blink;
    animation-delay: var(--delay);
    box-shadow: 0 0 20px var(--color), 0 0 20px var(--color) inset;
  }

  @keyframes blink {
    0% {
      opacity: 0;
    }
    50% {
      opacity: 1;
    }
    100% {
      opacity: 0;
    }
  }
</style>

<div style={`--delay: ${delay}s; --duration: ${delay + 1}s; --radius: ${radius}px; --color: rgba(${delay * 15}, 199, 25, ${1 / delay}); --top: ${delay}`}>
</div>