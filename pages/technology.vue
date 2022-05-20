<template>
    <div class="technology">
        <div class="technology__container">
            <div class="title"><span class="title__number">03</span> space launch 101</div>
            <div class="technology__content" v-if="technology">
              <div class="text__container">
                <div class="technology__nav">
                    <span :class="index === 0 ? 'selected' : ''" @click="index = 0">1</span>
                    <span :class="index === 1 ? 'selected' : ''" @click="index = 1">2</span>
                    <span :class="index === 2 ? 'selected' : ''" @click="index = 2">3</span>
                </div>
                <div class="text">
                    <div class="common">the terminology...</div>
                    <h3 class="name">{{ technology[index].name }}</h3>
                    <p class="description">{{ technology[index].description }}</p>
                </div>
              </div>
              <div class="technology__img">
                <img class="img__portrait" :src="require(`@/assets/${technology[index].images.portrait}`)">
                <img class="img__landscape" :src="require(`@/assets/${technology[index].images.landscape}`)">
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
      technology: null,
      index: 0,
    };
  },
  mounted() {
    this.technology = data.technology;
  },
};
</script>


<style lang="scss">

.technology {
    background-image: url("../assets/technology/background-technology-desktop.jpg");
    background-size: cover;
    background-position: center;
    background-attachment: fixed;
    padding: 12% 0 10% 10%;
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    z-index: -1000;
    &__container {
        margin-top: 40px;
    }
    @media (max-width: 1040px) {
      padding-left: 0;
    }
}

.technology__content {
  display: flex;
  justify-content: space-between;
  align-items: center;
  grid-gap: 32px;
  gap: 32px;
}

.technology__nav {
  display: flex;
  flex-direction: column;
  gap: 15px;
}

.technology__nav span {
    width: 80px;
    height: 80px;
    cursor: pointer;
    border-radius: 50%;
    display: flex;
    justify-content: center;
    align-items: center;
    border: 1px solid hsla(0,0%,100%,.25);
    transition: .2s;
}
.technology__nav span:hover {
  border: 1px solid rgb(255, 255, 255);
}
.selected {
  background-color: white;
  color: black;
}

.text__container {
    display: flex;
    justify-content: space-between;
    grid-gap: 80px;
    gap: 80px;
}

.text {
  max-width: 450px;
}

.common {
  font-size: 18px;
  text-transform: uppercase;
  letter-spacing: 2.7px;
}

.description {
  line-height: 27px;
  margin-bottom: 30px;
  text-align: justify;
}

.technology__img {
      img {
        max-width: 100%;
      }
      .img__portrait {
        @media (max-width: 767px) {
          display: none;
        }
      }
      .img__landscape {
        min-height: 170px;
        @media (min-width: 768px) {
          display: none;
        }
      }
    }

@media (max-width: 1040px) {
  .technology__content {
    display: flex;
    flex-direction: column-reverse;
  }
  .text__container {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  .technology__nav {
    display: flex;
    flex-direction: row;
  }
}


</style>