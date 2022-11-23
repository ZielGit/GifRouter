<template>
    <div>
        <h1>Search Gif</h1>
        <div class="row">
            <div v-for="gif in gifs" class="col-12 col-md-3">
                <span :key="gif.id">
                    {{ gif.title }}
                </span>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data: () => ({
        gifs: {},
    }),
    created() {
        this.getGifs();
    },
    methods: {
        async getGifs() {
            const res = await fetch("https://api.giphy.com/v1/gifs/search?api_key=IGvt90bSMcE0dhKhcT4uLHTycvybOecy&q=pikachu");
            const { data } = await res.json();

            this.gifs = data;
        },
    },
}
</script>