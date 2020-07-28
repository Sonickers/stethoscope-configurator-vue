<template>
  <div class="container has-background-light py-4 px-4">
    <div class="columns">
      <div class="column is-two-thirds">
        <header-title />
        <forms v-model="form" />
      </div>
      <div class="column">
        <result-product :form="form" />
        <action-buttons/>
      </div>
    </div>
  </div>
</template>

<script>
import headerTitle from "./header-title";
import forms from "./forms";
import resultProduct from "./result-product";
import actionButtons from './action-buttons'

export default {
  components: {
    headerTitle,
    forms,
    resultProduct,
    actionButtons
  },
  data() {
    return {
      form: {},
    };
  },
};
</script>