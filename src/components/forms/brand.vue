<template>
  <div>
    <div class="control">
      <h2 class="pb-2">Brand</h2>
      <button
        class="button mr-3 is-primary"
        :class="{ 'is-active' :active && active.id == brand.id, 'is-outlined': !active || active.id != brand.id }"
        v-for="brand in brands"
        :key="brand.id"
        @click="$emit('selected', brand)"
      >{{ brand.name }}</button>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    brands: Array,
    active: Object
  },
};
</script>