<script>
  import '../app.postcss'
  import '@skeletonlabs/skeleton/themes/theme-skeleton.css'
  import '@skeletonlabs/skeleton/styles/all.css'
  import { AppBar, AppRail, AppRailTile, AppShell } from '@skeletonlabs/skeleton'
  import Icon from '@iconify/svelte';
  import { page } from '$app/stores';

  const tileUrls = ['/', '/page2', '/page3']
</script>

<AppShell>
  <svelte:fragment slot="header">
    <AppBar>
      <svelte:fragment slot="lead">(icon)</svelte:fragment>
      Sveltekit Monorepo Boilerplate
      <svelte:fragment slot="trail">(actions)</svelte:fragment>
      </AppBar>
  </svelte:fragment>
  <svelte:fragment slot="sidebarLeft">
    <AppRail>
      <AppRailTile tag="a" href={tileUrls[0]} class="{tileUrls[0] === $page.url.pathname ? '!bg-primary-500' : ''}"><Icon icon="fa:home" height="20" /></AppRailTile>
      <AppRailTile tag="a" href="/my/page/route">(icon)</AppRailTile>
      <AppRailTile tag="a" href="/my/page/route">(icon)</AppRailTile>
    </AppRail>
  </svelte:fragment>
  <div class="container mx-auto h-screen flex">
    <slot />
  </div>
  <svelte:fragment slot="pageFooter">Page Footer</svelte:fragment>
</AppShell>
