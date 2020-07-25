<template>
    <div>
        <h2 class="pb-2">Brand</h2>
        <div class="control">
            <button class="button mr-3 is-rounded is-outlined is-primary" v-for="brand in brands" :key="brand.id"> {{ brand.name }} </button>
            <hr>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        brands: Array
    }
}
</script>