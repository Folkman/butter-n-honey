<script lang="ts">
import { Button, Row, Col, Card, CardBody, Form, FormGroup, Input } from 'sveltestrap'

const action = "https://gmail.us21.list-manage.com/subscribe/post?u=30955d0e25c1de81241a7ced8&amp;id=fd1fdfb434&amp;f_id=00fea9e1f0"

let fname = ''
let lname = ''
let email = ''
</script>

<div id="plan-form" class="plan-form">
  <Row class="p-2 text-center">
    <Col>
      <Card color="primary">
        <CardBody class="py-4">
          <Form {action} method="POST">
            <FormGroup floating label="First name">
              <Input name="FNAME" bind:value={fname} placeholder="First name" required />
            </FormGroup>
            <FormGroup floating label="Last name">
              <Input name="LNAME" bind:value={lname} placeholder="Last name" />
            </FormGroup>
            <FormGroup floating label="Email">
              <Input name="EMAIL" bind:value={email} type="email" placeholder="Email" required />
            </FormGroup>

            <!-- real people should not fill this in and expect good things - do not remove this or risk form bot signups-->
            <div style="position: absolute; left: -5000px;" aria-hidden="true">
              <input type="text" tabindex="-1" />
            </div>

            <Button class="button" type="submit" color="light">Send Me the Plan!</Button>
            <p class="my-3">
              <small>
                By downloading the plan, you are subscribing to receive emails and offers. You can 
                unsubscribe at any time.
              </small>
            </p>
            <a href="http://eepurl.com/ioJMfQ" title="Mailchimp - email marketing made easy and fun">
              <img src="https://eep.io/mc-cdn-images/template_images/branding_logo_text_dark_dtp.svg">
            </a>
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

  max-width: 800px;
  margin: 0 auto;
}
</style>
