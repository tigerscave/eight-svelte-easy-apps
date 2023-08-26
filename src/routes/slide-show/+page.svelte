<script>
  import { images } from "./imageData.js";
  import Slide from "./Slide.svelte";
  import Thumbnail from "./Thumbnail.svelte";
  let imageShowingIndex = 0;

  $: image = images[imageShowingIndex];

  const nextSlide = () => {
    if (imageShowingIndex === images.length - 1) {
      imageShowingIndex = 0;
    } else {
      imageShowingIndex += 1;
    }
  };

  const prevSlide = () => {
    if (imageShowingIndex === 0) {
      imageShowingIndex = images.length - 1;
    } else {
      imageShowingIndex -= 1;
    }
  };

  const goToSlide = (number) => (imageShowingIndex = number);
</script>

<body>
  <h2>ここは何県でしょうか？</h2>
  <main>
    <div class="container">
      <Slide
        image={image.src}
        altTag={image.name}
        slideNo={image.id + 1}
        totalSlides={images.length}
      />
    </div>
    <div class="container">
      <button on:click={prevSlide}>←</button>
      <button on:click={nextSlide}>→</button>
    </div>

    <div class="thumbnails-row">
      {#each images as { id, src, name }}
        <Thumbnail
          thumbImg={src}
          altTag={name}
          {id}
          selected={imageShowingIndex === id}
          on:click={() => goToSlide(id)}
        />
      {/each}
    </div>
  </main>
</body>

<style>
  h2 {
    text-align: center;
  }
  main {
    width: 440px;
    height: 333px;
    margin: 0 auto;
  }

  .container {
    display: flex;
    gap: 8px;
    margin-top: 8px;
  }

  button {
    all: unset;
    width: 220px;
    border: 1px solid black;
    border-radius: 4px;
    box-sizing: border-box;
    text-align: center;
    padding: 4px 0;
    cursor: pointer;
  }
  .thumbnails-row {
    margin-top: 10px;
    width: 150%;
    display: flex;
    align-self: flex-end;
  }
</style>
