<template>
    <div class="destination">
	<div class="destination__img"></div>
	<div class="destination__container">
		<div class="title"><span class="number">01</span> pick your destination</div>
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
                    <div class="destination__distance">
                        <h4>avg. distance</h4>
                        <span>{{ destinations[index].distance }}</span>
                    </div>
                    <div class="destination__travel">
                        <h4>est. travel time</h4>
                        <span>{{ destinations[index].travel }}</span>
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
        margin-top: 10rem;
        padding: 0 60px 0 80px;
        &__description {
            line-height: 27px;
            margin-bottom: 30px;
            text-align: justify;
        }
    }

    .destination__nav {
        cursor: pointer;
    }

    h2 {
        font-family: "Bellefair", serif;
        font-size: 100px;
        font-weight: 100;
    }

    .number {
        color: #ffffff40;
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

    .title {
        margin-bottom: 4rem;
        font-size: 28px;
        letter-spacing: 4.2px;
    }

    .title, .destination__name, span, .destination__distance, .destination__travel {
        text-transform: uppercase;
    }

    .destination__content {
        display: flex;
        justify-content: space-evenly;
    }

    .destination__nav {
        display: flex;
        grid-gap: 30px;
        gap: 30px;
    }

    .destination__info {
        display: flex;
        justify-content: space-between;
    }

    .destination__name {
        margin: 25px 0 25px 0;
    }
    .text {
        width: 350px;
    }

</style>