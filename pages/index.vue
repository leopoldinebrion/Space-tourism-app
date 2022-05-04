<template>
    <div class="home">
        <div class="home__img"><img src="../assets/home/background-home-desktop.jpg" alt=""></div>
        <div class="home__grid">
            <div class="home__content">
                <p class="subtitle">So, you want to travel to</p>
                <h1>Space</h1>
                <p>Let’s face it; if you want to go to space, you might as well genuinely go to 
                outer space and not hover kind of on the edge of it. Well sit back, and relax 
                because we’ll give you a truly out of this world experience!</p>
            </div>
            <div class="explore">
                <NuxtLink to="/destination" class="explore__btn">Explore</NuxtLink>
            </div>
        </div>
    </div>
</template>

<style scoped lang="scss">

    .home {
        margin-top: 10rem;
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

    .subtitle {
        font-size: 1.6rem;
        font-weight: 100;
        line-height: 1em;
        letter-spacing: 3px;
        text-transform: uppercase;
    }

    p {
        line-height: 1.4em;
    }

    .explore__btn {
        position: relative;
        background-color: white;
        color: black;
        border-radius: 50%;
        width: 16rem;
        height: 16rem;
        display: flex;
        justify-content: center;
        align-items: center;
        font-size: 2rem;
        font-family: 'Bellefair', serif;
        text-transform: uppercase;
        transition: outline 0.3s ease-in;
        &:hover {
            outline: 2rem solid rgba(255, 255, 255, 0.1);
        }
    }

    @media (max-width: 1092px) {
        .home__grid {
            display: flex;
            flex-direction: column;
        }
        .explore {
            margin-top: 50px;
        }
    }

    @media (max-width: 424px) {
        .home__content {
            padding: 124px 24px 0 24px;
        }
    }
</style>

