<script lang="ts">
import type { PageData } from './$types'
import { showNotification } from '$lib/store'

export let data: PageData

$: if (data.path === 'thanks') showNotification.set(true)
</script>
