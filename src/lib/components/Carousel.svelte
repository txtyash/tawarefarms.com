<!-- Carousel.svelte -->
<script>
  import { onMount } from 'svelte';

  export let images = [
    'https://placehold.co/600x400',
    'https://placehold.co/600x400',
    'https://placehold.co/600x400',
    'https://placehold.co/600x400'
  ];

  let currentIndex = 0;

  function nextImage() {
    currentIndex = (currentIndex + 1) % images.length;
  }

  onMount(() => {
    const interval = setInterval(nextImage, 2000);
    return () => clearInterval(interval);
  });
</script>

<div class="carousel">
  {#each images as image, index}
    <img
      src={image}
      alt={`Carousel image ${index + 1}`}
      class="carousel-image"
      class:active={index === currentIndex}
    />
  {/each}
</div>

<style>
  .carousel {
    position: relative;
    width: 100%;
    height: 400px;
    overflow: hidden;
  }

  .carousel-image {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    object-fit: cover;
    opacity: 0;
    transition: opacity 0.5s ease-in-out;
  }

  .carousel-image.active {
    opacity: 1;
  }
</style>