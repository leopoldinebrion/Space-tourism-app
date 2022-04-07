<template>
  <div class="app">
    <div class="nav">
      <div class="logo"><img src="@/assets/shared/logo.svg" alt="Logo" /></div>
        <div class="mobile_menu">
          <img src="../assets/shared/icon-hamburger.svg" alt="icon menu" @click="toggleMenu" />
        </div>
        <ul class="links">
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
    <Nuxt />
  </div>
</template>

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
      &.nuxt-link-exact-active::after {
        background-color: #fff;
        opacity: 1;
        transform: translateX(0);
      }
    }
  }

.mobile_menu {
  display: none;
}

span {
  font-weight: 700;
  margin-right: 0.5em;
}

// tab

@media (max-width: 990px) {
  span {
    display: none;
  }
}


// mobile

@media (max-width: 780px) {
  .mobile_menu {
    display: inline-block;
    margin-right: 2rem;
  }
  .links {
    display: none;
  }
}

</style>
