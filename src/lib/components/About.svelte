<script lang="ts">
  import { Container, Button, Row, Col } from 'sveltestrap'
  import AboutImg from '$lib/assets/about.jpg?w=1400;1200;1000;800;600;500&metadata'
  import ResponsiveImg from '$lib/components/ResponsiveImg.svelte'

  const bnhUrl = 'https://shopbutternhoney.etsy.com'
</script>

<div id="about" class="about">
  <Row>
    <Col>
      <h1 class="text-center">About</h1>
      <p class="verse text-center">
        "Butter and honey shall he eat, that he may know to refuse the evil, and choose the good."
        - Isaiah 7:15
      </p>
      <p>
        Hi! 👋🏼 Let me introduce myself!
      </p>
      <p>
        My name is Monik, and I am a mother to a 3-year-old girl and a wife to a software
        engineer.
      </p>
      <p>
        I have been a Christian for more than 23 years and am passionate about studying God's
        word. However, although I read and studied the Bible, I felt something was missing.
        I didn't know it then, but I was having a hard time organizing my studies and the thoughts
        that came with them. Reading and studying became boring that sometimes I skipped them.
      </p>
      <p>
        Then, I was reminded of this method of writing down information that I had learned when I
        was in nursing school which is called a correlation map. I remember I enjoyed doing that!
        Also, I actually would try to map when I read a book or sometimes when I studied but never
        thought that I could use it regularly for my personal Bible studies!
      </p>
      <p>
        That's when Scripture Mapping Journal came into the picture! Mapping has changed my Bible
        studies! It has helped me to dig deeper into God's word and made it personal to me! I
        think about mapping all day long and always look forward to mapping more when I'm finished
        with one!
      </p>
      <p>
        It's my desire to equip and empower others, especially women and mothers who desire to
        teach their children, to learn to study God's word for themselves not only through
        Scripture Mapping but also through other tools that will come to fruition in the future.
      </p>
      <p>
        I can't wait to share more!
      </p>
    </Col>
  </Row>
  <Row>
    <Col>
      <div class="image">
        <ResponsiveImg alt="Four scripture mapping journals spread out" images={AboutImg} />
      </div>
      <div class="text-center pt-3">
        <Button size="lg" color="primary" class="button" href={bnhUrl}>Shop Butter n' Honey</Button>
      </div>
    </Col>
  </Row>
</div>

<style lang="scss">
.about {
  h1 {
    text-transform: uppercase;
  }

  .verse {
    font-style: italic;
  }

  .image {
    margin: 30px 0;
  }

  p {
    font-size: 20px;
  }

  :global(.button) {
    color: white;
    text-transform: uppercase;
  }
}
</style>
