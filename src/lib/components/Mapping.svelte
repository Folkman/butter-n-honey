<script lang="ts">
import { Row, Col, Image, Container, Card, CardBody } from 'sveltestrap'
import MappingImg from '$lib/assets/mapping.jpg?w=1000;700&metadata'
import ResponsiveImg from '$lib/components/ResponsiveImg.svelte'
</script>

<div id="mapping" class="mapping text-center">
  <Container fluid class="px-0">
    <Row>
      <Col xs="12">
        <ResponsiveImg
          alt="Open scripture mapping journal with a mapped scripture"
          images={MappingImg}
        />
      </Col>
      <Col xs=12 class="p-5">
        <h1>What is Scripture Mapping?</h1>
        <p>
          It's a visual Bible study method to dig deeper into God's word. Map a verse, a word, a Bible
          character, a topic, an object, and many more!
        </p>
      </Col>
    </Row>
  </Container>
</div>

<style lang="scss">
@import '../../global.scss';

.mapping {
  h1 {
    text-transform: uppercase;
  }

  color: white;
  background-color: map-get($theme-colors, "secondary");
}
</style>