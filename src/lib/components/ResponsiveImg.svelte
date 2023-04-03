<script lang="ts">
export let images: any[] = []
export let mobileImages: any[] = []
export let alt: string

const aspect = images[0].height / images[0].width
const aspectMobile = (mobileImages.length ? mobileImages[0].height / mobileImages[0].width : aspect)

let height = 500

const setHeight = (event: Event): void => {
  const img = event.currentTarget as HTMLImageElement
  const useAspect  = img.height > img.width ? aspectMobile : aspect
  height = img.width * useAspect
}
</script>

<div class="image" style:--image-height="{height}px">
  <picture>
    {#each images as image}
      <source srcset={image.src} media="(min-width: {image.width}px)" />
    {/each}
    {#each mobileImages as image}
      <source srcset={image.src} media="(min-width: {image.width}px)" />
    {/each}
    <img on:load={setHeight} {alt} src={images[0].src} />
  </picture>

  <slot />
</div>

<style lang="scss">
.image {
  position: relative;
  width: 100%;
  height: var(--image-height);

  img {
    position: absolute;
    object-fit: cover;
    top: 0;
    bottom: 0;
    right: 0;
    left: 0;
    height: 100%;
    width: 100%;
  }
}
</style>
