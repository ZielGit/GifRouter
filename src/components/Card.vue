<template>
    <div class="card">
        <img
            class="card-img-top"
            :src="gif.images.original.url"
            :alt="gif.id"
            height="250"
            loading="lazy"
        >
        <div class="card-body">
            <h4 class="card-title">{{ gif.title }}</h4>
        </div>
    </div>
</template>

<script>
export default {
    props: ["gif"],
}
</script>
