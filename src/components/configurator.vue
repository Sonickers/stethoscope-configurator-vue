<template>
  <div class="container has-background-light py-4 px-4">
    <header-title />
    <div class="columns">
      <div class="column is-two-thirds">
        <forms v-model="form" />
      </div>
      <div class="column">
        <result-product />
      </div>
    </div>
  </div>
</template>

<script>
import headerTitle from "./header-title";
import forms from "./forms";
import resultProduct from "./result-product";

export default {
  components: {
    headerTitle,
    forms,
    resultProduct,
  },
  data() {
    return {
      form: {},
    };
  },
};
</script>