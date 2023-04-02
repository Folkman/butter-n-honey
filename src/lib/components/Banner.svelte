<script lang="ts">
import Img from '$lib/assets/main.jpg?w=2500;2000;1500;1000;700&metadata'
import ImgMobile from '$lib/assets/main-mobile.jpg?w=500;400;300&metadata'
import ResponsiveImg from '$lib/components/ResponsiveImg.svelte'
import { Button, Container, Row, Col } from 'sveltestrap'
import { jumpTo } from '$lib/helper'
</script>

<div class="banner">
  <Container fluid class="px-0">
    <Row>
      <Col>
        <ResponsiveImg
          alt="Scripture mapping journals arranged in a plus"
          images={Img}
          mobileImages={ImgMobile}
        >
          <div class="call-out text-center">
            <h1>
              Ready to <br />
              Scripture map?
            </h1>
            <Button class="button" on:click={() => jumpTo('#plan-form')}>Get a Mapping Plan!</Button>
          </div>
        </ResponsiveImg>
      </Col>
    </Row>
  </Container>
</div>

<style lang="scss">
.call-out {
  position: relative;
  display: flex;
  align-items: center;
  flex-direction: column;
  justify-content: center;
  height: 100%;
  color: white !important;

  h1 {
    padding: 15px;
  }

  :global(.button) {
    color: white;
    text-transform: uppercase;
  }
}
</style>
