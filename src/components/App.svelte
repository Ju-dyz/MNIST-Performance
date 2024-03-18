<script>
  import { goto } from '$app/navigation';
  // Placeholder array for MNIST dataset images
  const mnistImages = [
    '/mnist.png',
  ];

  // Placeholder for hyperlinks - update with your actual URLs and names
  const links = [
    { name: 'Layers', url: 'src/routes/layers.svelte' },
    { name: 'Batch Size', url: 'src/routes/batch_size.svelte' },
    { name: 'Epoch', url: 'src/routes/epoch.svelte' },
    { name: 'Learning Rate', url: 'src/routes/learning.svelte' },
    { name: 'Regularization', url: 'src/routes/regularize.svelte' },
  ];
</script>

<div>
  <h1>MNIST DATASET PERFORMANCE</h1>

  <div class="mnist-container">
    {#each mnistImages as image}
      <img src={image} alt="MNIST Image">
    {/each}
  </div>

  <div class="links-container">
    {#each links as link}
      <div class="link" on:click={() => goto(link.url)}>
        {link.name}
      </div>
    {/each}
  </div>
</div>

<style>
  :global(body) {
    background-image: url('/background.png');
    background-size: 250% 60%; /* Cover the entire page */
    background-position: center; /* Center the background image */
    /* background-color: rgba(237, 241, 245, 0.39); */
    margin: 0;
  }
  
  h1 {
    text-align: center;
    margin: 2rem 0;
  }

  .mnist-container {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 10px;
    margin-bottom: 2rem;
  }

  .mnist-container img {
    width: calc(35% - 10px);
    height: 10;
  }

  .links-container {
    display: flex;
    justify-content: space-around;
    margin: auto;
    max-width: 960px;
  }

  .link {
    display: inline-block;
    background-color: #edeeee;
    padding: 1rem 2rem;
    margin: 0.5rem;
    text-align: center;
    cursor: pointer;
    transition: background-color 0.3s ease;
  }

  .link:hover {
    background-color: #e0e0e0;
  }
</style>