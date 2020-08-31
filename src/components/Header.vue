<template>
  <header class="header">
    <Container class="header-container">
      <router-link to="/" class="logo">Instagram</router-link>

      <form class="search">
        <input type="text" placeholder="Search" />
      </form>

      <nav>
        <router-link to="/">
          <IconHome />
          <IconHomeFill />
        </router-link>
        <router-link to="/direct">
          <IconDirect />
          <IconDirectFill />
        </router-link>
        <router-link to="/explore">
          <IconExplore />
          <IconExploreFill />
        </router-link>
        <router-link to="/profile">Profile</router-link>
      </nav>
    </Container>
  </header>
</template>

<script>
import IconHome from '@/icons/home.svg'
import IconHomeFill from '@/icons/home-fill.svg'
import IconDirect from '@/icons/direct.svg'
import IconDirectFill from '@/icons/direct-fill.svg'
import IconExplore from '@/icons/explore.svg'
import IconExploreFill from '@/icons/explore-fill.svg'
import Container from '@/components/Container'

export default {
  name: 'MainHeader',
  components: {
    Container,
    IconHome,
    IconHomeFill,
    IconDirect,
    IconDirectFill,
    IconExplore,
    IconExploreFill
  }
}
</script>

<style scoped>
.header {
  border-bottom: 1px solid rgb(var(--b6a));
}
.header-container {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  align-items: center;
  padding: 20px;
}
.logo {
  font-weight: bold;
  font-size: 1.6rem;
  text-decoration: none;
}

.search {
  text-align: center;

  input {
    width: 215px;
    height: 28px;
    border: 1px solid rgb(var(--b6a));
    background-color: rgb(var(--b3f));
    border-radius: 4px;
    padding-left: 20px;
    padding-right: 20px;
  }
}
</style>
