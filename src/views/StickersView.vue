<template>
    <div>
        <h1>Search Sticker</h1>
        <Search @buscar="getStickers" />
        <div class="row">
            <div v-for="sticker in stickers" :key="sticker.id" class="col-12 col-md-4 g-3">
                <Card :gif="sticker" />
            </div>
        </div>
    </div>
</template>

<script>
import Card from '../components/Card.vue';
import Search from '../components/Search.vue';

export default {
    data: () => ({
        stickers: [],
    }),
    created() {
        this.getStickers();
    },
    methods: {
        async getStickers(busqueda = "pokemon") {
            if (busqueda.trim() === "") {
                alert("Sin busqueda");
                return;
            }

            const res = await fetch(`https://api.giphy.com/v1/stickers/search?api_key=IGvt90bSMcE0dhKhcT4uLHTycvybOecy&q=${busqueda}`);
            const { data } = await res.json();
            this.stickers = data;
        },
    },
    components: { Card, Search },
};
</script>