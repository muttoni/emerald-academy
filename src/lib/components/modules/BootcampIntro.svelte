<script>
  import Button from "../atoms/Button.svelte";
  import { formatDate } from "$lib/utils";

  export let bootcamp;
</script>

<div class="column">
  <p id="date">
    {#if bootcamp.active }
      Kickoff: {formatDate(bootcamp.dateStart)}
    {:else}
      Completed on {bootcamp.dateEnd}
    {/if}
  </p>
  <h1>
    {bootcamp.title}
  </h1>
  <p id="time-to-finish">
    Part Time - {bootcamp.timeToFinish}
  </p>
  <p id="description">
    {bootcamp.description}
  </p>
  <div class="buttons">
    <Button
      on:click={() => window.open(bootcamp.repository, "_blank")}
      class="small ghost"
    >
      <svg
        xmlns="http://www.w3.org/2000/svg"
        id="Layer_1"
        viewBox="0 0 47.999998 48.000002"
        width="22"
        height="22"
        ><path
          fill="current-color"
          d="M23.928 1.15C11 1.15.514 11.638.514 24.566c0 10.343 6.75 19.105 15.945 22.265 1.148.144 1.58-.574 1.58-1.15v-4.02c-6.465 1.436-7.902-3.16-7.902-3.16-1.005-2.73-2.586-3.45-2.586-3.45-2.154-1.435.144-1.435.144-1.435 2.298.144 3.59 2.442 3.59 2.442 2.156 3.59 5.46 2.586 6.753 2.01.142-1.58.86-2.585 1.435-3.16-5.17-.574-10.63-2.585-10.63-11.635 0-2.585.862-4.596 2.442-6.32-.287-.575-1.005-3.017.288-6.177 0 0 2.01-.574 6.464 2.442 1.866-.574 3.877-.718 5.888-.718 2.01 0 4.022.286 5.89.717 4.453-3.016 6.464-2.442 6.464-2.442 1.293 3.16.43 5.602.287 6.177a9.29 9.29 0 0 1 2.44 6.32c0 9.05-5.458 10.918-10.63 11.492.863.718 1.58 2.155 1.58 4.31v6.464c0 .574.432 1.292 1.58 1.15 9.338-3.16 15.946-11.924 15.946-22.266-.143-12.785-10.63-23.27-23.558-23.27z"
          id="path20"
          clip-rule="evenodd"
          fill-rule="evenodd"
        /></svg
      >
      Repository
    </Button>
    {#if bootcamp.active}
      <Button
        on:click={() => window.open(bootcamp.signUp, "_blank")}
        class="small ghost"
      >
        <svg
          width="20px"
          height="20px"
          viewBox="0 0 20 20"
          xmlns="http://www.w3.org/2000/svg"
          ><path
            d="M10.595 5.196l.446 1.371a4.135 4.135 0 0 1 1.441-.795c.59-.192 1.111-.3 1.582-.362l-.43-1.323a9.465 9.465 0 0 0-1.58.368 5.25 5.25 0 0 0-1.459.741zm.927 2.855l.446 1.371a4.135 4.135 0 0 1 1.441-.795c.59-.192 1.111-.3 1.582-.362l-.43-1.323a9.465 9.465 0 0 0-1.58.368 5.21 5.21 0 0 0-1.459.741zm.928 2.854l.446 1.371a4.135 4.135 0 0 1 1.441-.795c.59-.192 1.111-.3 1.582-.362l-.43-1.323a9.465 9.465 0 0 0-1.58.368 5.21 5.21 0 0 0-1.459.741zm-7.062 2.172l.43 1.323a8.745 8.745 0 0 1 1.492-.636 4.141 4.141 0 0 1 1.633-.203l-.446-1.371a5.25 5.25 0 0 0-1.615.257 9.406 9.406 0 0 0-1.494.63zM3.533 7.368l.43 1.323a8.825 8.825 0 0 1 1.492-.636 4.141 4.141 0 0 1 1.633-.203L6.643 6.48a5.263 5.263 0 0 0-1.616.258 9.406 9.406 0 0 0-1.494.63zm.927 2.855l.43 1.323a8.745 8.745 0 0 1 1.492-.636 4.141 4.141 0 0 1 1.633-.203L7.57 9.335a5.25 5.25 0 0 0-1.615.257 9.417 9.417 0 0 0-1.495.631zm6.604-8.813a5.26 5.26 0 0 0-3.053 2.559 5.257 5.257 0 0 0-3.973-.275C1.515 4.514.069 6.321.069 6.321l4.095 12.587c.126.387.646.477.878.143.499-.719 1.46-1.658 3.257-2.242 1.718-.558 2.969.054 3.655.578.272.208.662.06.762-.268.252-.827.907-2.04 2.61-2.593 1.799-.585 3.129-.389 3.956-.1.385.134.75-.242.625-.629L15.819 1.203s-2.232-.612-4.755.207zm-.113 13.846a5.208 5.208 0 0 0-3.141.044c-1.251.406-2.127.949-2.699 1.404L1.866 6.722c.358-.358 1.187-1.042 2.662-1.521 1.389-.451 2.528-.065 3.279.378l3.144 9.677zm6.894-2.689c-.731-.032-1.759.044-3.01.451a5.205 5.205 0 0 0-2.567 1.81L9.124 5.151c.346-.8 1.04-1.782 2.43-2.233 1.474-.479 2.547-.413 3.047-.334l3.244 9.983z"
          /></svg
        >
        Sign Up
      </Button>
    {/if}
  </div>
</div>

<style>
  .column {
    display: flex;
    flex-direction: column;
  }

  #date {
    font-size: var(--font-size-xs);
    color: var(--primary);
    font-family: var(--font-accent);
    margin-bottom: 2em;
  }

  h1 {
    font-size: clamp(1.4rem, 15vw, 2rem);
    margin-bottom: 0.6em;
    margin-top: 0;
  }

  #time-to-finish {
    font-size: var(--font-size-xs);
    color: var(--primary);
    font-family: var(--font-accent);
    text-transform: uppercase;
    letter-spacing: 0.3em;
    margin-bottom: 1.4em;
  }

  #description {
    margin-bottom: 3em;
    max-width: 45ch;
  }

  .buttons {
    display: flex;
    gap: 0.9em;
  }
</style>
