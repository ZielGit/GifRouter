<template>
    <div>
        <h1>Search Gif</h1>
        <div class="row">
            <div v-for="gif in gifs" :key="gif.id" class="col-12 col-md-4 g-3">
                <div class="card">
                    <img class="card-img-top" :src="gif.images.original.url" alt="Image" height="250">
                    <div class="card-body">
                        <h4 class="card-title">{{ gif.title }}</h4>
                        <a href="#" class="btn btn-primary">Download</a>
                    </div>
                </div>
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