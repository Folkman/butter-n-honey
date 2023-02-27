<script lang="ts">
import Img from '$lib/assets/main.jpg?w=2500;2000;1500;1000;700&metadata'
import ImgMobile from '$lib/assets/main-mobile.jpg?w=500;400;300&metadata'
import { Button, Container, Row, Col } from 'sveltestrap'

const aspect = (Img[0].height / Img[0].width)
const aspectMobile = (ImgMobile[0].height / ImgMobile[0].width)

let height = 500

const setMainHeight = (event: Event): void => {
  const img = event.currentTarget as HTMLImageElement
  const useAspect  = img.height > img.width ? aspectMobile : aspect
  height = img.width * useAspect
}
</script>

<Container fluid class="px-0">
  <Row>
    <Col>
      <div class="home" style:--home-height="{height}px">
        <picture>
          {#each Img as image}
            <source srcset={image.src} media="(min-width: {image.width}px)" />
          {/each}
          {#each ImgMobile as image}
            <source srcset={image.src} media="(min-width: {image.width}px)" />
          {/each}
          <img
            on:load={setMainHeight}
            alt="Scripture mapping journals arranged in a plus"
            src={Img[0].src}
          />
        </picture>

        <div class="call-out">
          <h1>
            Ready to <br />
            Scripture map?
          </h1>
          <Button class="button">Get a Mapping Plan!</Button>
        </div>
      </div>
    </Col>
  </Row>
</Container>

<style lang="scss">
.home {
  position: relative;
  width: 100%;
  height: var(--home-height);
}

img {
  position: absolute;
  object-fit: cover;
  height: 100%;
  width: 100%;
}

.call-out {
  position: relative;
  display: flex;
  align-items: center;
  flex-direction: column;
  justify-content: center;
  height: 100%;
  color: white !important;
  text-align: center;

  h1 {
    padding: 15px;
  }

  :global(.button) {
    color: white;
    text-transform: uppercase;
  }
}
</style>
