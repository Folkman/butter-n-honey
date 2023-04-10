<script lang="ts">
import { Row, Col } from 'sveltestrap'
import MappingImg from '$lib/assets/mapping.jpg?w=700;500;375;&metadata'
import ResponsiveImg from '$lib/components/ResponsiveImg.svelte'
</script>

<div id="mapping" class="mapping text-center">
  <Row>
    <Col xs="12" md="6">
      <ResponsiveImg
        alt="Open scripture mapping journal with a mapped scripture"
        images={MappingImg}
      />
    </Col>
    <Col xs=12 md="6">
      <div class="mapping-text p-5">
        <h1>What is Scripture Mapping?</h1>
        <p>
          Scripture mapping is a Bible study method where you visually analyze a Bible verse, a
          word, or a Bible character to gain a deeper understanding and to see connections you may
          have never seen before. It's a great tool to enhance your Bible study and spiritual
          growth!
        </p>
      </div>
    </Col>
  </Row>
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