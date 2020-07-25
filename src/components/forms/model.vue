<template>
    <div>
        <h2 class="pb-2">Model</h2>
        <div class="control">
            <button class="button mr-3 is-rounded is-outlined is-primary" v-for="model in models" :key="model.id"> {{ model.name }} </button>
            <hr>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        models: Array
    }
}
</script>