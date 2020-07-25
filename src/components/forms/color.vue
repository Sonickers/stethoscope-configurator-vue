<template>
    <div>
        <h2 class="pb-2">Color</h2>
        <div class="control">
            <button class="button mr-3 is-outlined is-rounded" :class="color.color" v-for="color in colors" :key="color.id"> {{ color.name }} </button>
            <hr>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        colors: Array,
        active: Object
    }
}
</script>