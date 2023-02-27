<script lang="ts">
import { Button, Row, Col, Card, CardBody, Form, FormGroup, Input } from 'sveltestrap'
</script>

<div class="plan-form">
  <Row class="p-4 text-center">
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
</div>

<style lang="scss">
.plan-form {
  :global(.button) {
    text-transform: uppercase;
  }
}
</style>