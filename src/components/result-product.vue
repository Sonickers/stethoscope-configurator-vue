<template>
  <div class="card">
    <div class="card-image"></div>
    <div class="card-content">
      <div class="content">
        <p class="title has-text-primary has-text-centered pt-5">Summary</p>
        <div class="media">
          <div class="media-content">
            <figure class="image is-4by3">
              <img v-if="image" :src="image" />
            </figure>
          </div>
        </div>
        <div class="columns">
          <p class="column has-text-left">Brand</p>
          <p class="column has-text-right has-text-weight-bold">{{ brandName }}</p>
        </div>
        <div class="columns">
          <p class="column has-text-left">Model</p>
          <p class="column has-text-right has-text-weight-bold">{{ modelName }}</p>
        </div>
        <div class="columns">
          <p class="column has-text-left">Color</p>
          <p class="column has-text-right has-text-weight-bold">{{ colorName }}</p>
        </div>
        <div class="columns">
          <p class="column has-text-left">Cost</p>
          <p class="column has-text-right has-text-weight-bold">{{ cost }}</p>
        </div>
        <!-- Add delivery time to every color value -->
        <!-- <p>Delivery:</p>
        <p class="has-text-right has-text-weight-bold">
          <time datetime="2016-1-1">1 Jan 2016</time>
        </p>-->
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    form: {
      type: Object,
      default: () => ({}),
    },
  },
  computed: {
    image() {
      if (!this.form || !this.form.color) return require(`@/assets/images/no-image.png`);
      return require(`@/assets/images/${this.form.color.img}`);
    },
    modelName() {
      if (!this.form.model) {
        return '-'
      }
      return this.form.model.name
    },
    brandName() {
      if (!this.form.brand) {
        return '-'
      }
      return this.form.brand.name
    },
    colorName() {
      if (!this.form.color) {
        return '-'
      }
      return this.form.color.name
    },
    cost () {
      const sum = (this.form.model?.cost ?? 0) + (this.form.brand?.cost ?? 0)
      return sum + ' $'
    }
  },
};
</script>