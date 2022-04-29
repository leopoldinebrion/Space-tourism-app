<template>
    <div class="destination">
        <div class="destination__img"></div>
        <!-- <div class="destination__container">
            <h1><span>01</span> pick your destination</h1> -->
    <div class="page-content" v-if="destinations"> 
      <aside class="item-content">
        <div class="page-menu">
          <span :class="index === 0 ? 'selected' : ''" @click="index = 0"
            >moon</span
          >
          <span :class="index === 1 ? 'selected' : ''" @click="index = 1"
            >mars</span
          >
          <span :class="index === 2 ? 'selected' : ''" @click="index = 2"
            >europa</span
          >
          <span :class="index === 3 ? 'selected' : ''" @click="index = 3"
            >titan</span
          >
        </div>
        <h1 class="item-name">{{ destinations[index].name }}</h1>
        <p class="item-description">{{ destinations[index].description }}</p>
        <div class="item-info">
          <div class="item-distance">
            <h4>avg. distance</h4>
            <span>{{ destinations[index].distance }}</span>
          </div>
          <div class="item-travel">
            <h4>est. travel time</h4>
            <span>{{ destinations[index].travel }}</span>
          </div>
        </div>
      </aside>
    </div>
</div>
</template>

<script>
import data from "../assets/data.json";

export default {
  data() {
    return {
      index: 0,
      destinations: null,
    };
  },
  mounted() {
    this.destinations = data.destinations;
  },
};
</script>
            <!-- <div class="content">
                <img :src="require(`@/assets/${destinations[index].images.png}`)">
            </div>
        </div>
    </div>
</template>

<script>

import data from "../assets/data.json"

export default {

    data() {
        return {
            destinations: null,
            index: 0,
        }
    },

    mounted() {
        this.destinations = data.destinations;
    }
}

</script> -->

<style scoped lang="scss">

    .destination {
        margin-top: 10rem;
    }

    .destination__img {
        background: url("../assets/destination/background-destination-desktop.jpg");
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 900px;
        z-index: -1;
        object-fit: cover;
        @media (max-width: 990px) {
            background: url("../assets/destination/background-destination-tablet.jpg"); ;
            background-size: cover;
        }

        @media (max-width: 780px) {
            background: url("../assets/destination/background-destination-mobile.jpg"); ;
            background-size: cover;
        }
    }

    h1 {
        text-transform: uppercase;
    }

</style>