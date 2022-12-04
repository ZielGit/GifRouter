<template>
    <div>
        <form @submit.prevent="$emit('buscar', busqueda)" class="row g-3">
            <div class="col-auto">
                <label for="" class="col-form-label">Search: </label>
            </div>
            <div class="col-auto">
                <input v-model="busqueda" class="form-control" type="text">
            </div>
            <div class="col-auto">
                <button class="btn btn-warning" type="submit">Search</button>
            </div>
        </form>
    </div>
</template>

<script>
export default {
    data: () => ({
        busqueda: "",
    }),
};
</script>
