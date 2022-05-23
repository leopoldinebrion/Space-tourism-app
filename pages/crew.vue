<template>
  <div class="crew">
    <div class="crew__container">
      <div class="title"><span class="title__number">02</span> meet your crew</div>
      <div class="crew__content" v-if="crew">
        <div class="text">
          <h4 class="role">{{ crew[i].role }}</h4>
          <h3 class="name">{{ crew[i].name }}</h3>
          <p class="bio">{{ crew[i].bio }}</p>
          <div class="crew__nav">
            <span
              @click="selectedIndex(0)" class="selected points"
            ></span>
            <span
              @click="selectedIndex(1)" class="points"
            ></span>
            <span
              @click="selectedIndex(2)" class="points"
            ></span>
            <span
              @click="selectedIndex(3)" class="points"
            ></span>
          </div>
        </div>
        <div class="crew__img">
          <img :src="require(`@/assets/${crew[i].images.png}`)">
        </div>  
      </div>
    </div>
  </div>
</template>

<script>

import data from "../assets/data.json";
export default {
  data() {
    return {
      crew: [],
      i: 0,
    };
  },

 methods: {
    selectedIndex(index) {
      let points = document.querySelectorAll('.points')
      points.forEach((active) => {
        active.classList.remove('selected')
      })
      points[index].classList.add('selected')
      this.i = index;
    },
  },
  created() {
    this.crew = data.crew;
  },
};

</script>

<style scoped lang="scss">

.crew {
    background-image: url("../assets/crew/background-crew-desktop.jpg");
    background-size: cover;
    background-position: center;
    background-attachment: fixed;
    padding: 12% 10% 10%;
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    z-index: -1000;
    &__container {
      margin-top: 40px;
    }
}

.crew__content {
  display: flex;
  align-items: center;
  grid-gap: 130px;
  margin-top: -120px;
}

.role, .name {
  margin-bottom: 18px;
}

.bio {
  line-height: 27px;
  margin-bottom: 30px;
  text-align: justify;
}

.text {
  max-width: 430px;
}

.crew__nav {
  display: flex;
  margin-top: 5rem;
}

.crew__nav span {
  position: relative;
  width: 13px;
  height: 13px;
  border-radius: 50%;
  background-color: #ffffff34;
  margin: 0 10px;
  cursor: pointer;
}

.selected {
  background-color: white !important;
}

.crew__nav span:hover {
  background-color: #ffffff71;
}

img {
  max-width: 100%;
}

  @media (max-width: 1105px) {
    .crew__content {
      flex-direction: column-reverse;
      justify-content: center;
      text-align: center;
      gap: 40px;
      margin-top: 0;
    }

    .text {
      display: flex;
      flex-direction: column;
      align-items: center;
    }
  }

 @media (max-width: 1180px) {
  .crew__container {
    margin-top: 60px;
  }
 }

</style>