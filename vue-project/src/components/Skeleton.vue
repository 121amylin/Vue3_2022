<script setup>
    import { ref, onMounted } from 'vue'
    const DataValue = ref([]);
    const isLoad = ref(true);

    const LoadImg = (imgUrl) => {
        const imgArr = [...imgUrl];
        let i = 0;
        imgArr.forEach(src => {
            const img = new Image();
            img.src = src;
            img.onload = () => {
                i += 1;
                if (i === imgArr.length) {
                    isLoad.value = false;
                }
            }
        })
    }

    onMounted(() => {
        fetch('https://610cd85966dd8f0017b76eb5.mockapi.io/api/card')
            .then(res => res.json()).then(res => {
                DataValue.value = res;
                const imgArr = res.map(item => [item.avatar, item.content]);
                LoadImg([].concat(...imgArr));
            });
    })
</script>

<template>
    <div :class="['card', {load: isLoad}]" v-for="item in DataValue" :key="item.id">
        <header>
            <div class="photo">
                <img :src="item.avatar">
            </div>
            <p>{{ isLoad ? "" : item.username }}</p>
        </header>
        <p>{{ isLoad ? "" : item.text }}</p>
        <main>
            <img :src="item.content">
        </main>
    </div>
</template>

<style lang="scss" scoped>
* {
    padding: 0;
    margin: 0;
    box-sizing: border-box;
}

img {
    display: block;
}

html,
body {
    width: 100%;
    height: 100%;
    background-color: #e1e1e1;
    display: flex;
    justify-content: center;
    align-items: center;
}

#app {
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: space-around;

    align-items: center;
    flex-wrap: wrap;
    padding: 35px;
}

.card {
    width: 300px;
    height: auto;
    border-radius: 10px;
    overflow: hidden;
    background-color: #fff;
    box-shadow: 0 1px 5px rgba(0, 0, 0, 0.2);
    margin-bottom: 50px;

    >p {
        font-size: 14px;
        padding: 0 10px;
        margin-bottom: 10px;
    }

    header {
        width: 100%;
        display: flex;
        justify-content: flex-start;
        align-items: center;
        padding: 10px;

        >div {
            margin-right: 10px;

            >img {
                border-radius: 50%;
            }
        }

        >p {
            font-size: 13px;
        }
    }

    img {
        opacity: 1;
        transition: opacity .3s;
    }
}

.load {
    width: 300px;
    height: 380px;
    border-radius: 10px;
    overflow: hidden;
    background-color: #fff;

    >header {
        width: 100%;
        display: flex;
        justify-content: flex-start;
        align-items: center;
        padding: 10px;

        >div {
            width: 30px;
            height: 30px;
            border-radius: 50px;
            margin-right: 10px;
            background-color: #ededed;

            >img {
                border-radius: 50%;
            }
        }

        >p {
            font-size: 13px;
            display: block;
            width: 40%;
            height: 18px;
            background-color: #ededed;
        }
    }

    >p {
        font-size: 14px;
        margin: 0 10px 10px 10px;
        display: block;
        width: 70%;
        height: 18px;
        background-color: #ededed;
    }

    >main {
        width: 100%;
        height: 300px;
        background-color: #ededed;
    }

    img {
        opacity: 0;
    }

}

@keyframes loading {
    to {
        background-position-x: -20%;
    }
}

.load {
    .photo,
    p,
    main {
        background: linear-gradient(100deg,
                rgba(256, 256, 256, 0) 30%,
                rgba(256, 256, 256, 0.5) 50%,
                rgba(256, 256, 256, 0) 30%) #ededed;
        background-size: 200% 100%;
        background-position-x: 180%;
        animation: 2s loading ease-in-out infinite;
    }
}
</style>