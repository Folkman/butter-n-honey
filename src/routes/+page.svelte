<script lang="ts">
  import '../global.scss'
  import TopBar from '$lib/components/TopBar.svelte'
  import Banner from '$lib/components/Banner.svelte'
  import PlanForm from '$lib/components/PlanForm.svelte'
  import Mapping from '$lib/components/Mapping.svelte'
  import About from '$lib/components/About.svelte'
  import Footer from '$lib/components/Footer.svelte'
  import { Container } from 'sveltestrap'
</script>

<TopBar />
<Container class="px-0">
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

<style lang="scss">
.spacer {
  height: 60px;
}
</style>
