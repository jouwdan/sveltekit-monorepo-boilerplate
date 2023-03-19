<script>
  import '../app.postcss'
  import '@skeletonlabs/skeleton/themes/theme-skeleton.css'
  import '@skeletonlabs/skeleton/styles/all.css'
  import {
    AppBar,
    AppRail,
    AppRailTile,
    AppShell,
    LightSwitch
  } from '@skeletonlabs/skeleton'
  import Icon from '@iconify/svelte'
  import { page } from '$app/stores'

  const tileUrls = ['/', '/page2', '/page3']
</script>

<AppShell>
  <svelte:fragment slot="header">
    <AppBar class="h-20 justify-center">
      <svelte:fragment slot="lead">
        <a href="/" class="font-bold text-xl">SvelteKit Monorepo Boilerplate</a>
      </svelte:fragment>
      <svelte:fragment slot="trail">
        <LightSwitch />
      </svelte:fragment>
    </AppBar>
  </svelte:fragment>
  <svelte:fragment slot="sidebarLeft">
    <AppRail width="w-20">
      <AppRailTile
        tag="a"
        label="home"
        href={tileUrls[0]}
        class={tileUrls[0] === $page.url.pathname ? '!bg-primary-500' : ''}
        ><Icon icon="fa:home" height="20" /></AppRailTile
      >
      <AppRailTile tag="a" href="/my/page/route">(icon)</AppRailTile>
      <AppRailTile tag="a" href="/my/page/route">(icon)</AppRailTile>
    </AppRail>
  </svelte:fragment>
  <slot />
  <svelte:fragment slot="pageFooter">
    <div
      class="h-12 flex items-center justify-end pr-8 bg-surface-100-800-token"
    >
      <span>&copy; Copyright Your Name 2023, All Rights Reserved</span>
    </div>
  </svelte:fragment>
</AppShell>
