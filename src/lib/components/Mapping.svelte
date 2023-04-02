<script lang="ts">
import { Row, Col, Image, Container, Card, CardBody } from 'sveltestrap'
import MappingImg from '$lib/assets/mapping.jpg?w=1000;700&metadata'
import ResponsiveImg from '$lib/components/ResponsiveImg.svelte'
</script>

<div id="mapping" class="mapping text-center">
  <Container fluid class="px-0">
    <Row>
      <Col xs="12" sm="6">
        <ResponsiveImg
          alt="Open scripture mapping journal with a mapped scripture"
          images={MappingImg}
        />
      </Col>
      <Col xs=12 sm="6">
        <div class="mapping-text p-5">
          <h1>What is Scripture Mapping?</h1>
          <p>
            It's a visual Bible study method to dig deeper into God's word. Map a verse, a word, a
            Bible character, a topic, an object, and many more!
          </p>
        </div>
      </Col>
    </Row>
  </Container>
</div>

<style lang="scss">
@import '../../global.scss';

.mapping {
  color: white;
  background-color: map-get($theme-colors, "secondary");

  .mapping-text {
    h1 {
      text-transform: uppercase;
      margin-bottom: 25px;
    }

    p {
      font-size: 20px;
    }
  }
}
</style>