<script lang="ts">
import { Container, Button, Row, Col, Card, CardBody, Form, FormGroup, Input } from 'sveltestrap'
</script>

<div id="plan-form" class="plan-form">
  <Container>
    <Row class="p-2 text-center">
      <Col>
        <Card color="primary">
          <CardBody class="py-4">
            <Form>
              <FormGroup floating label="First name">
                <Input placeholder="First name" />
              </FormGroup>
              <FormGroup floating label="Last name">
                <Input placeholder="Last name" />
              </FormGroup>
              <FormGroup floating label="Email">
                <Input placeholder="Email" />
              </FormGroup>
              <Button class="button" color="light">Send Me the Plan!</Button>
            </Form>
          </CardBody>
        </Card>
      </Col>
    </Row>
  </Container>
</div>

<style lang="scss">
.plan-form {
  :global(.button) {
    text-transform: uppercase;
  }

  max-width: 800px;
  margin: 0 auto;
}
</style>