<script lang="ts">
import InstagramImg from '$lib/assets/instagram.png'
import FacebookImg from '$lib/assets/facebook.png'
import YouTubeImg from '$lib/assets/youtube.png'

const instagramUrl = 'https://www.instagram.com/shopbutternhoney/'
const facebookUrl = 'https://www.facebook.com/shopbutternhoney'
const youTubeUrl = 'https://www.youtube.com/@shopbutternhoney'
</script>

<footer class="text-center">
  <a href={instagramUrl}>
    <img src={InstagramImg} alt="Instagram icon" />
  </a>
  <div class="spacer" />
  <a href={facebookUrl}>
    <img src={FacebookImg} alt="Facebook icon" />
  </a>
  <div class="spacer" />
  <a href={youTubeUrl}>
    <img src={YouTubeImg} alt="YouTube icon" />
  </a>
</footer>

<style lang="scss">
footer {
  margin-top: 10px;
}
.spacer {
  display: inline-block;
  width: 50px;
}
</style>
