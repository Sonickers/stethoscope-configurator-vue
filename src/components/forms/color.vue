<template>
  <div>
    <h2 class="pb-2">Color</h2>
    <div class="control">
      <button
        class="button mr-3 is-rounded"
        :class="getColorClasses(color)"
        v-for="color in colors"
        :key="color.id"
        @click="$emit('selected', color)"
      >{{ color.name }}</button>
      <hr />
    </div>
  </div>
</template>

<script>
export default {
  props: {
    colors: Array,
    active: Object,
  },
  methods: {
    getColorClasses(color) {
      return {
        "is-active": this.active && this.active.id == color.id,
        "is-outlined": !this.active || this.active.id != color.id,
        [color.color]: true,
      };
    },
  },
};
</script>