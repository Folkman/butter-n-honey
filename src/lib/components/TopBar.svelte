<script lang="ts">
  import Logo from '$lib/assets/logo.png?w=180&webp'
  import {
    Navbar,
    NavbarBrand,
    NavbarToggler,
    Collapse,
    Nav,
    NavItem,
    NavLink,
    Image,
  } from 'sveltestrap'
  import { jumpTo } from '$lib/helper'

  const bnhUrl = 'https://shopbutternhoney.etsy.com'

  let isOpen = false
  let href: string | null = null

  const toggle = () => isOpen = !isOpen
  const goTo = (anchor: string): void => {
    href = anchor
    toggle()
  }
  const scroll = (): void => {
    if (!href) return

    jumpTo(href)
    href = null
  }
</script>

<Navbar sticky="top" color="white">
  <NavbarBrand>
    <Image class="me-auto" alt="Butter n' Honey logo" src={Logo} />
  </NavbarBrand>
  <NavbarToggler class="me-2" on:click={toggle} />
  <Collapse {isOpen} navbar on:close={scroll}>
    <Nav navbar>
      <NavItem>
        <NavLink on:click={toggle} href="/">Home</NavLink>
      </NavItem>
      <NavItem>
        <NavLink on:click={() => goTo('#plan-form')}>Get a mapping plan</NavLink>
      </NavItem>
      <NavItem>
        <NavLink on:click={() => goTo('#mapping')}>What is scripture mapping?</NavLink>
      </NavItem>
      <NavItem>
        <NavLink on:click={() => goTo('#about') }>About</NavLink>
      </NavItem>
      <NavItem>
        <NavLink on:click={toggle} href={bnhUrl}>SHOP BUTTER N' HONEY</NavLink>
      </NavItem>
    </Nav>
  </Collapse>
</Navbar>
