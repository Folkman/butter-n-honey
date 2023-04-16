<script lang="ts">
import { Button, Row, Col, Card, CardBody, Form, FormGroup, Input, Alert } from 'sveltestrap'

const action = "https://assets.mailerlite.com/jsonp/400940/forms/85643725490882481/subscribe"

let fname = ''
let lname = ''
let email = ''
let fields: { [key: string]: string }
let submitted = false
let error = false
let errors: { name: string[]; email: string[] } = { name: [], email: [] }

$: fields = {
  name: fname.trim(),
  last_name: lname.trim(),
  email: email.trim(),
  'ml-submit': '1',
  anticsrf: 'true'
}

const signUp = async (event: SubmitEvent): Promise<void> => {
  event.preventDefault()
  if (invalid()) return

  try {
    const form = event.target as HTMLFormElement
    const formData = new FormData();
    Object.keys(fields).forEach(key => formData.append(`fields[${key}]`, fields[key]))
    const resp = await fetch(form.action, { method: 'POST', body: formData })
    const body = await resp.json()
    if (resp.status !== 200) throw resp.status

    if (body.success) {
      submitted = true
    } else {
      errors = body.errors.fields
    }
  } catch {
    error = true
  }
}

const invalid = (): boolean => {
  errors = { name: [], email: [] }
  if (!fname.trim().length) errors.name = ['First name is required.']
  if (!email.trim().length) errors.email = ['Email is required']
  return !!errors.name.length || !!errors.email.length
}

const resetForm = (): void => {
  fname = ''
  lname = ''
  email = ''
  errors = { name: [], email: [] }
  error = false
  submitted = false
}
</script>

<div id="plan-form" class="plan-form">
  <Row class="p-2 text-center">
    <Col>
      {#if submitted}
        <Alert color="success" isOpen toggle={resetForm} fade={false}>
          Yay! Your mapping plan is on its way to your inbox.
          Check your spam folder just in case!
        </Alert>
      {:else if error}
        <Alert color="danger" isOpen toggle={resetForm} fade={false}>
          Something went wrong. You can try again, or email
          <a href="mailto:help@butternhoney.com">
            help@butternhoney.com
          </a>
        </Alert>
      {:else}
        <Card color="primary">
          <CardBody class="pt-4 px-4">
            <Form {action} method="POST" on:submit={signUp}>
              <FormGroup floating label="First name">
                <Input
                  bind:value={fname}
                  invalid={!!errors.name?.length}
                  feedback={errors.name}
                  placeholder="First name"
                />
              </FormGroup>
              <FormGroup floating label="Last name">
                <Input bind:value={lname} placeholder="Last name" />
              </FormGroup>
              <FormGroup floating label="Email">
                <Input
                  bind:value={email}
                  invalid={!!errors.email?.length}
                  feedback={errors.email}
                  type="email"
                  placeholder="Email"
                />
              </FormGroup>

              <Button class="button" type="submit" color="light">Send Me the Plan!</Button>
              <p class="mt-3">
                <small>
                  By downloading the plan, you are subscribing to receive emails and offers. You can 
                  unsubscribe at any time.
                </small>
              </p>
            </Form>
          </CardBody>
        </Card>
      {/if}
    </Col>
  </Row>
</div>

<style lang="scss">
.plan-form {
  :global(.button) {
    text-transform: uppercase;
  }

  :global(.invalid-feedback) {
    text-align: left !important;
  }

  max-width: 800px;
  margin: 0 auto;
}
</style>
