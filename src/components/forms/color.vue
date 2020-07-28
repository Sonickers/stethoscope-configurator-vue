<template>
  <div>
    <h2 class="pb-2">Color</h2>
    <div class="control">
      <button
        class="button mr-3 is-rounded is-primary"
        :class="getColorClasses(color)"
        v-for="color in colors"
        :key="color.id"
        @click="$emit('selected', color)"
      >
        <span class="square-color" :style="{'background-color': color.hex}"></span>
        {{ color.name }}
      </button>
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
      };
    },
  },
};
</script>

<style scoped>
.square-color {
  display: inline-block;
  width: 1em;
  height: 1em;
  margin-right: 5px;
  border-radius: 50%;
}
</style>