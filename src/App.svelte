<script>
  import { onMount } from 'svelte';
  let count = 0;
  onMount(() => {
    const interval = setInterval(() => count++, 1000);
    return () => {
      clearInterval(interval);
    };
  });
</script>

<div class="app">
  <header>
    <h1>Ratemy</h1>
    <nav>
      <a href="/">Rate</a>
      <a href="/">Leaderboard</a>
    </nav>
  </header>
  <p>Counter: {count}!</p>
  <div class="choices">
    <div class="left-choice">
      <iframe
        width="100%"
        height="350"
        src="https://www.youtube.com/embed/Wakmo63rttg"
        title="YouTube video player"
        frameborder="0"
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
        allowfullscreen
      />
      <div class="select-button">
        <button>Select</button>
      </div>
    </div>
    <div class="right-choice">
      <iframe
        width="100%"
        height="350"
        src="https://www.youtube.com/embed/TwtVTMyzna8"
        title="YouTube video player"
        frameborder="0"
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
        allowfullscreen
      />
      <div class="select-button">
        <button>Select</button>
      </div>
    </div>
    <div class="vote">
      <button>Vote</button>
    </div>
  </div>
  <footer>
    <p>
      By <a href="https://mfcl.io">MFCL</a>.
      <a href="https://github.com/mfcochauxlaberge/ratemy">Source code</a>.
    </p>
  </footer>
</div>

<style>
  * {
    margin: 0;
    padding: 0;
  }

  .app {
    margin: 10px;
    padding: 10px;
    border: 1px solid #ccc;
    background: #fff;
  }

  header {
    display: grid;
    justify-content: center;
    padding: 10px;
    background: red;
  }

  h1 {
    padding: 10px;
    text-align: center;
    /* background: rgba(255, 255, 255, 0.2); */
  }

  nav {
    display: grid;
    grid-gap: 10px;
    grid-template-columns: 1fr 1fr;
  }

  nav > a {
    display: block;
    padding: 10px;
    width: 120px;
    text-align: center;
    background: rgba(0, 0, 0, 0.2);
  }

  .choices {
    display: grid;
    grid-template-columns: 1fr 1fr;
  }

  @media (max-aspect-ratio: 1) {
    .choices {
      grid-template-columns: 1fr;
      grid-template-rows: 1fr / 1fr;
    }
  }

  .left-choice {
    border: 1px solid red;
  }

  .right-choice {
    border: 1px solid blue;
  }

  .select-button {
    padding: 10px;
    text-align: center;
    background: #ccc;
  }

  .select-button > button {
    padding: 10px;
    border: 1px solid #666;
    border-radius: 10px;
  }

  .vote {
    display: grid;
    justify-content: center;
    padding: 10px;
    border: 1px solid black;
  }

  .vote > button {
    padding: 10px;
    border: 1px solid #666;
    border-radius: 10px;
  }

  footer {
    display: grid;
    justify-content: center;
    padding: 10px;
    border: 1px solid black;
  }
</style>
