<template>
  <div class="app">
    <div class="nav">
      <div class="logo"><img src="@/assets/shared/logo.svg" alt="Logo" /></div>
        <ul class="links">
          <li>
            <NuxtLink to="/"><span class="number">00</span> HOME</NuxtLink>
          </li>
          <li>
            <NuxtLink to="/destination"><span class="number">01</span> DESTINATION</NuxtLink>
          </li>
          <li>
            <NuxtLink to="/crew"><span class="number">02</span> CREW</NuxtLink>
          </li>
          <li>
            <NuxtLink to="/technology"><span class="number">03</span> TECHNOLOGY</NuxtLink>
          </li>
        </ul>
        <div class="mobile__menu" @click="toggleMenu = true">
          <img src="../assets/shared/icon-hamburger.svg" alt="icon mobile menu" />
        </div>
        <div v-if="toggleMenu" class="mobile__menu-item">
            <img  @click="toggleMenu = false" src="../assets/shared/icon-close.svg" alt="close mobile menu">
            <ul>
              <li>
                <NuxtLink to="/"><span>00</span> HOME</NuxtLink>
              </li>
              <li>
                <NuxtLink to="/destination"><span>01</span> DESTINATION</NuxtLink>
              </li>
              <li>
                <NuxtLink to="/crew"><span>02</span> CREW</NuxtLink>
              </li>
              <li>
                <NuxtLink to="/technology"><span>03</span> TECHNOLOGY</NuxtLink>
              </li>
          </ul>
        </div>
    </div>
    <Nuxt />
  </div>
</template>

<script>

export default {
  data() {
    return {
      toggleMenu: false,
    }
  }
}

</script>

<style lang="scss">

.nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding-top: 2.4rem;
  padding-left: 2.4rem;
}

.links {
  display: flex;
  justify-content: space-between;
  width: 60%;
  background-color: #ffffff0d;
  backdrop-filter: blur(1.5rem);
  letter-spacing: 1.8px;
  font-size: 16px;
  padding: 0 48px 0 48px;
  transition: all .5s ease;
  li {
      padding: 39px 0 39px 0;
      position: relative;
      &::after {
        content: '';
        position: absolute;
        width: 100%;
        height: 3px;
        left: 0;
        bottom: -1px;
        opacity: 0;
        transform: translateX(-100%);
        transition: 0.2s;
      }
      &:hover::after {
        background-color: #fff;
        opacity: 1;
        transform: translateX(0);
      }
    }
  }

  .nuxt-link-exact-active::after {
        content: "";
        width: 100%;
        height: 3px;
        background-color: #fff;
        position: absolute;
        left: 0;
        bottom: -1px;
      }

.mobile_menu {
  display: none;
}

span {
  font-weight: 700;
  margin-right: 0.5em;
}

 .mobile__menu-item {
  backdrop-filter: blur(1.5rem);
  transition: transform 0.15s ease-in;
  position: fixed;
  width: 250px;
  top: 0;
  right: 0;
  bottom: 0;
  z-index: 99;
  display: flex;
  align-items: center;
  padding-left: 30px;
  img {
    position: absolute;
    top: 30px;
    right: 30px;
  }
}

img {
  cursor: pointer;
}


@media (min-width: 780px) {
  .mobile__menu {
    display: none;
  }
}
// tab

@media (max-width: 1090px) {
  .number {
    display: none;
  }
}


// mobile

@media (max-width: 780px) {
  .mobile__menu {
    display: inline-block;
    margin-right: 2rem;
  }
  .links {
    display: none;
  }

  li {
    padding: 0 0 20px 0;
    a {
      letter-spacing: 1.5px;
    }
  }
}

</style>
