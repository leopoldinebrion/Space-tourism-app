<template>
  <div class="app">
    <div class="nav">
      <div class="logo"><img src="@/assets/shared/logo.svg" alt="Logo" /></div>
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
        <div class="icon">
          <img src="../assets/shared/icon-hamburger.svg" alt="icon menu" @click="toggleMenu" />
        </div>
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
  li {
      padding: 39px 0 39px 0;
  }
}

.nuxt-link-exact-active {
    border-bottom: 2px solid white;    
    padding: 39px 0 39px 0;
}

@media (max-width: 990px) {
  span {
    display: none;
  }
}
</style>
