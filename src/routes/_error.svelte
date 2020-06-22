<script>
  export let status;
  export let error;

  const dev = process.env.NODE_ENV === "development";
</script>

<style>
  .Error404 {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  .Error404-image figure {
    margin: 0;
    padding: 0;
    text-align: right;
  }

  .Error404-image img {
    width: 250px;
    margin: 2em 0 0 0;
    transform: translatey(0px);
    animation: float 8s ease-in-out infinite;
  }

  @keyframes float {
    0% {
      transform: translatey(0px);
    }
    50% {
      transform: translatey(-40px);
    }
    100% {
      transform: translatey(0px);
    }
  }

  h1,
  p {
    margin: 0 auto;
  }

  h1 {
    font-size: 2.8em;
    font-weight: 700;
    margin: 0 0 0.5em 0;
  }

  p {
    margin: 1em auto;
  }

  @media (min-width: 480px) {
    h1 {
      font-size: 4em;
    }
  }
</style>

<svelte:head>
  <title>{status}</title>
</svelte:head>

<div class="Error404">
  <div class="Error404-message">
    <h1>Hmmm!</h1>
    <p>No encontrmos lo que buscabas.</p>
    <p>{status} - {error.message}</p>
    {#if dev && error.stack}
      <pre>{error.stack}</pre>
    {/if}
  </div>
  <div class="Error404-image">
    <figure>
      <img src="https://arepa.s3.amazonaws.com/img404.png" alt="Error404" />
    </figure>
  </div>
</div>
