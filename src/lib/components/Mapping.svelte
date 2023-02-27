<script lang="ts">
import Mapping from '$lib/assets/mapping.jpg'
import { Row, Col, Image, Container, Card, CardBody } from 'sveltestrap'
</script>

<div class="mapping text-center">
  <Row>
    <Col class="px-0">
      <Image fluid alt="Open scripture mapping journal with a mapped scripture" src={Mapping} />
    </Col>
    <Col class="p-5">
      <h1>What is Scripture Mapping?</h1>
      <p>
        It's a visual Bible study method to dig deeper into God's word. Map a verse, a word, a Bible
        character, a topic, an object, and many more!
      </p>
    </Col>
  </Row>
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