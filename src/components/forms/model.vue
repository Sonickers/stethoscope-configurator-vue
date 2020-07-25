<template>
  <div>
    <h2 class="pb-2">Model</h2>
    <div class="control">
      <button
        class="button mr-3 is-rounded is-primary"
        :class="{ 'is-active' :active && active.id == model.id, 'is-outlined': !active || active.id != model.id }"
        v-for="model in models"
        :key="model.id"
        @click="$emit('selected', model)"
      >{{ model.name }}</button>
      <hr />
    </div>
  </div>
</template>

<script>
export default {
  props: {
    models: Array,
    active: Object,
  },
};
</script>