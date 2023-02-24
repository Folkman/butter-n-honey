<script lang="ts">
import MainImg from '$lib/assets/main.jpg?w=2500;2000;1500;1000;700;500;400;300&metadata'
import { Button, Container, Row, Col } from 'sveltestrap'

let aspect = (MainImg[0].height / MainImg[0].width)
let height = 500

const setMainHeight = (event: Event): void => {
  const img = event.currentTarget as HTMLImageElement
  height = img.width * aspect
}
</script>

<Container fluid class="px-0">
  <Row>
    <Col>
      <div class="home" style:--home-height="{height}px">
        <picture>
          {#each MainImg as image}
            <source srcset={image.src} media="(min-width: {image.width}px)" />
          {/each}
          <img
            on:load={(event) => setMainHeight(event)}
            alt="Scripture mapping journals arranged in a plus"
            src={MainImg[0].src}
          />
        </picture>
        <div class="call-out">
          <h1>Ready to Scripture map?</h1>
          <Button>Get a Mapping Plan!</Button>
        </div>
      </div>
    </Col>
  </Row>
</Container>

<style>
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
}
</style>
