<script lang="ts">
  import '../global.scss'
  import TopBar from '$lib/components/TopBar.svelte'
  import Banner from '$lib/components/Banner.svelte'
  import Mapping from '$lib/assets/mapping.jpg'
  import About from '$lib/assets/about.jpg'
  import { Button, Container, Row, Col, Input, Image } from 'sveltestrap'
</script>

<TopBar />
<Banner />

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
