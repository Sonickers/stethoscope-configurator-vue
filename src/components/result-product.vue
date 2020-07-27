<template>
  <div class="card">
    <div class="card-image"></div>
    <div class="card-content">
      <div class="media">
        <div class="media-content">
          <img v-if="image" :src="image" />
        </div>
      </div>

      <div class="content">
        <p class="subtitle has-text-primary has-text-centered">Summary</p>
        <div class="columns">
          <p class="column has-text-left">Model</p>
          <p class="column has-text-right">Littmann</p>
        </div>
        <p>Brand:</p>
        <p class="has-text-right has-text-weight-bold">Cardio</p>
        <p>Color:</p>
        <p class="has-text-right has-text-weight-bold">Deep Black</p>
        <p>Cost:</p>
        <p class="has-text-right has-text-weight-bold">$ 350</p>
        <br />
        <!-- Add delivery time to every color value -->
        <p>Delivery:</p>
        <p class="has-text-right has-text-weight-bold">
          <time datetime="2016-1-1">1 Jan 2016</time>
        </p>
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
      if (!this.form || !this.form.color) return "";
      return require(`@/assets/images/${this.form.color.img}`);
    },
  },
};
</script>