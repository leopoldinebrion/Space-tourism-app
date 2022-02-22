<template>
  <div class="app">
    <div class="nav">
      <div class="logo"><img src="@/assets/shared/logo.svg" alt="Logo" /></div>
        <ul class="links">
          <li>
            <NuxtLink to="/"><span>00</span> HOME</NuxtLink>
          </li>
          <li>
            <NuxtLink to="/"><span>01</span> DESTINATION</NuxtLink>
          </li>
          <li>
            <NuxtLink to="/"><span>02</span> CREW</NuxtLink>
          </li>
          <li>
            <NuxtLink to="/"><span>03</span> TECHNOLOGY</NuxtLink>
          </li>
        </ul>
    </div>
    <Nuxt />
  </div>
</template>

<style scoped>

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
  width: 40%;
  padding: 39px 48px;
  background-color: #ffffff0d;
  backdrop-filter: blur(1.5rem);
  letter-spacing: 1.8px;
  font-size: 16px;
}

</style>
