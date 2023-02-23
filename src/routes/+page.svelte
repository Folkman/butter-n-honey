<script lang="ts">
  import TopBar from '$lib/assets/components/TopBar.svelte'
  import { height, src as Main} from '$lib/assets/main.jpg?width=400&metadata'
  import Mapping from '$lib/assets/mapping.jpg'
  import About from '$lib/assets/about.jpg'
  import { Styles, Button, Container, Row, Col, Input, Image } from 'sveltestrap'

  let isOpen = false
</script>

<Styles />
<TopBar />

<Container class="px-0">
  <div class="text-center" style="height: {height}px; background-image: url({Main}); background-size: cover;">
    <Row>
      <Col>
        <h1>Ready to Scripture map?</h1>
        <Button>Get a Mapping Plan!</Button>
      </Col>
    </Row>
  </div>
</Container>

<Container>
  <Row>
    <Col>
      <Input placeholder="First name" />
      <Input placeholder="Last name" />
      <Input placeholder="Email" />
      <Button>Send Me the Plan!</Button>
    </Col>
  </Row>

  <Row>
    <Col>
      <Image fluid alt="Open scripture mapping journal with a mapped scripture" src={Mapping} />
      <h1>What is Scripture Mapping?</h1>
      <p>
        It's a visual Bible study method to dig deeper into God's word. Map a verse, a word, a Bible
        character, a topic, an object, and many more!
      </p>
    </Col>
  </Row>

  <Row>
    <Col>
      <h1>About</h1>
      <p>
        "Butter and honey shall he eat, that he may know to refuse the evil, and choose the good."
        -- Isa. 7:15
      </p>
      <p>
        Butter n' Honey is an Etsy shop that provides Bible study tools, such as Scripture mapping
        journals, to help others to discern between good & evil.
      </p>
      <Image fluid alt="Four scripture mapping journals spread out" src={About} />

      <Button>Shop Here</Button>
    </Col>
  </Row>
</Container>
