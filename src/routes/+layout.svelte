<script lang="ts">
import '/src/global.scss'
import TopBar from '$lib/components/TopBar.svelte'
import Banner from '$lib/components/Banner.svelte'
import PlanForm from '$lib/components/PlanForm.svelte'
import Mapping from '$lib/components/Mapping.svelte'
import About from '$lib/components/About.svelte'
import Footer from '$lib/components/Footer.svelte'
import { Container, Alert } from 'sveltestrap'
import { showNotification } from '$lib/store'
</script>

<TopBar />
<Container>
  <Alert color="success" isOpen={$showNotification} dismissible>
    Yay! Your mapping plan is on its way to your inbox. Check your spam folder just in case!
  </Alert>
  <Banner />
  <div class="spacer" />
  <PlanForm />
  <div class="spacer" />
  <Mapping />
  <div class="spacer" />
  <About />
  <div class="spacer" />
  <Footer />
  <div class="spacer" />
</Container>
<slot />

<style lang="scss">
.spacer {
  height: 60px;
}
</style>
