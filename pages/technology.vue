<template>
    <div class="technology">
        <img class="technology__background" src="../assets/technology/background-technology-desktop.jpg" alt="">
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


<style scoped lang="scss">

.technology__background { 
  position: fixed; 
  top: 0; 
  left: 0; 
  min-width: 100%;
  min-height: 100%;
  z-index: -1;
  background-position: center;
  background-size: cover;
}

.technology {
    padding: 10% 0 10% 10%;
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
    border: 1px solid #ffffff40;
    transition: .2s;
}
.technology__nav span:hover {
  border: 1px solid #ffffff;
}
.selected {
  background-color: #ffffff;
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

.name {
  margin-top: 10px;
  margin-bottom: 10px;
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

  .text {
    padding: 0 25px;
  }
}


</style>