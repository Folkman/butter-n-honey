<script lang="ts">
  import About from '$lib/assets/about.jpg'
  import { Container, Button, Row, Col, Image } from 'sveltestrap'

  const bnhUrl = 'https://shopbutternhoney.etsy.com'
</script>

<div id="about" class="about text-center">
  <Container>
    <Row>
      <Col>
        <h1>About</h1>
        <p class="verse">
          "Butter and honey shall he eat, that he may know to refuse the evil, and choose the good."
          -- Isa. 7:15
        </p>
        <p>
          Butter n' Honey is an Etsy shop that provides Bible study tools, such as Scripture mapping
          journals, to help others to discern between good & evil.
        </p>
      </Col>
    </Row>
  </Container>
  <Container fluid class="px-0">
    <Row>
      <Col>
        <div class="image">
          <Image fluid alt="Four scripture mapping journals spread out" src={About} />
        </div>

        <Button color="primary" class="button" href={bnhUrl}>Shop Here</Button>
      </Col>
    </Row>
  </Container>
</div>

<style lang="scss">
.about {
  margin-top: 30px;

  h1 {
    text-transform: uppercase;
  }

  .verse {
    font-style: italic;
  }

  .image {
    margin: 30px 0;
  }
  :global(.button) {
    color: white;
    text-transform: uppercase;
  }
}
</style>
