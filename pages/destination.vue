<template>
    <div class="destination">
        <!-- <div class="destination__img"></div> -->
        <div class="destination__container">
            <div class="title"><span class="title__number">01</span> pick your destination</div>
            <div class="destination__content" v-if="destinations">
                <div class="destination__planet-img">
                    <!-- <img :src="destinations[index].images.png" alt="destinations[index].name"> -->
                    <img :src="require(`@/assets/${destinations[index].images.png}`)">
                </div>
                <div class="text">
                    <div class="destination__nav">
                        <span :class="index === 0 ? 'selected' : ''" @click="index = 0">moon</span>
                        <span :class="index === 1 ? 'selected' : ''" @click="index = 1">mars</span>
                        <span :class="index === 2 ? 'selected' : ''" @click="index = 2">europa</span>
                        <span :class="index === 3 ? 'selected' : ''" @click="index = 3">titan</span>
                    </div>
                    <h2 class="destination__name">{{ destinations[index].name }}</h2>
                    <p class="destination__description">
                        {{ destinations[index].description }}
                    </p>
                    <div class="destination__info">
                        <div class="info__details subtitle2">
                            <span>avg. distance</span>
                            {{ destinations[index].distance }}
                        </div>
                        <div class="info__details subtitle2">
                            <span>est. travel time</span>
                            {{ destinations[index].travel }}
                        </div>
                    </div>
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
      index: 0,
      destinations: null,
    };
  },
  
  mounted() {
    this.destinations = data.destinations;
  },
};
</script>


<style scoped lang="scss">

    .destination {
        background-image: url("../assets/destination/background-destination-desktop.jpg");
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
        &__description {
            line-height: 27px;
            margin-bottom: 30px;
            text-align: justify;
        }
    }

    // .destination__img {
    //     background: url("../assets/destination/background-destination-desktop.jpg");
    //     position: absolute;
    //     top: 0;
    //     left: 0;
    //     width: 100%;
    //     height: 900px;
    //     z-index: -1;
    //     object-fit: cover;
    //     @media (max-width: 990px) {
    //         background: url("../assets/destination/background-destination-tablet.jpg");
    //         background-size: cover;
    //     }

    //     @media (max-width: 780px) {
    //         background: url("../assets/destination/background-destination-mobile.jpg");
    //         background-size: cover;
    //         height: 1050px;
    //     }
    // }


    .destination__name, span, .destination__distance, .destination__travel {
        text-transform: uppercase;
    }

    .destination__content {
        display: flex;
        justify-content: space-between;
        align-items: center;
    }

    .destination__nav {
        display: flex;
        grid-gap: 30px;
        gap: 30px;
        span {
            cursor: pointer;
        }
    }

    .selected::after {
    display: block;
    content: " ";
    position: relative;
    width: 100%;
    bottom: 0;
    padding-bottom: 7px;
    border-bottom: 3.5px solid white;
}

    .destination__info {
        display: flex;
        justify-content: space-between;
        border-top: 1px solid #383b4b;
        padding-top: 20px;
        margin-top: 50px;
        width: 100%;
    }

    .destination__name {
        margin: 25px 0 25px 0;
    }

    .text {
        width: 350px;
    }

    .info__details {
        display: flex;
        flex-direction: column;
        grid-gap: 10px;
        gap: 10px;
    }

    @media (max-width: 1180px) {
        .destination__content {
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        .destination__container {
            margin-top: 60px;
        }
        .text {
            margin-top: 40px;
            display: flex;
            flex-direction: column;
            align-items: center;
        }
    }
</style>