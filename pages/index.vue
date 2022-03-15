<template>
    <div class="home">
        <div class="home__img"><img src="../assets/home/background-home-desktop.jpg" alt=""></div>
        <div class="home__grid">
            <div class="home__content">
                <h3>So, you want to travel to</h3>
                <h1>Space</h1>
                <p>Let’s face it; if you want to go to space, you might as well genuinely go to 
                outer space and not hover kind of on the edge of it. Well sit back, and relax 
                because we’ll give you a truly out of this world experience!</p>
            </div>
            <div>
                <a href="#" class="large-button uppercase ff-serif text-dark bg-white">Explore</a>
            </div>
        </div>
    </div>
</template>

<style scoped lang="scss">

    .home {
        margin-top: 6rem;
    }

    .home__img {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 900px;
        z-index: -1;
        object-fit: cover;
        img {
            width: 100%;
            height: 100%;
        }
    }

    .home__content {
        width: 420px;
        text-align: justify;
    }

    .home__grid {
        display: flex;
        align-items: center;
        justify-content: space-between;
        margin: 0 8rem;
        padding: 2rem;
    }

    h1 {
        font-family: 'Bellefair', serif;
        text-transform: uppercase;
        font-weight: 200;
        font-size: 9rem;
    }

    h3 {
        font-size: 1.6rem;
        font-weight: 100;
        line-height: 1em;
        letter-spacing: 3px;
        text-transform: uppercase;
    }

    p {
        line-height: 1.4em;
    }

</style>

