<template>
  <div class="crew">
    <div class="crew__container">
      <div class="title"><span class="title__number">02</span> meet your crew</div>
      <div class="crew__content">
        <div class="text">
          <h4 class="role">{{ crew[index].role }}</h4>
          <h3 class="name">{{ crew[index].name }}</h3>
          <p class="bio">{{ crew[index].bio }}</p>
          <div class="crew__nav">
            <span
              @click="activeIndex" data-index="0" class="selected"
            ></span>
            <span
              @click="activeIndex" data-index="1"
            ></span>
            <span
              @click="activeIndex" data-index="2"
            ></span>
            <span
              @click="activeIndex" data-index="3"
            ></span>
          </div>
        </div>
        <div class="crew__img">
          <img :src="require(`@/assets/${crew[index].images.png}`)">
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
      crew: data.crew,
      index: 0,
    };
  },

  methods: {
    activeIndex(e) {
      this.index = e.target.getAttribute('data-index')
      document
        .querySelectorAll('span')
        .forEach((ele) => ele.classList.remove('selected'))
      e.target.classList.add('selected')
    }
  }
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

// .crew__img {
//   position: absolute;
//   bottom: 0;
//   right: 195px;
//   top: 67px;
// }

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
  aspect-ratio: 1;
  border-radius: 50%;
  background-color: rgba(255, 255, 255, 0.205);
  margin: 0 0.7rem;
}

.selected {
  background-color: rgb(255, 255, 255) !important;
}

.crew__nav span:hover {
  background-color: rgba(255, 255, 255, 0.445);
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