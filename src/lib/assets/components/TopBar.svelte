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
    Image
  } from 'sveltestrap'

  let isOpen = false
  const toggle = () => isOpen = !isOpen
</script>

<Navbar>
  <NavbarBrand>
    <Image class="me-auto" alt="Butter n' Honey logo" src={Logo} />
  </NavbarBrand>
  <NavbarToggler class="me-2" on:click={toggle} />
  <Collapse {isOpen} navbar>
    <Nav navbar>
      <NavItem>
        <NavLink href="#home">Home</NavLink>
      </NavItem>
      <NavItem>
        <NavLink href="#plan">Get a mapping plan</NavLink>
      </NavItem>
      <NavItem>
        <NavLink href="#mapping">What is scripture mapping?</NavLink>
      </NavItem>
      <NavItem>
        <NavLink href="#about">About</NavLink>
      </NavItem>
    </Nav>
  </Collapse>
</Navbar>

<style>

</style>
