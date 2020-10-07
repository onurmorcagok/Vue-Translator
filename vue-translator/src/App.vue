<template>
  <div class="container">
    <h1 class="text-center">Vue-Translator</h1>
    <h5 class="text-center">Vue.js with Translator</h5>
    <br />
    <div class="row">
      <div class="col-md-12 text-center">
        <TranslateForm></TranslateForm>
        <h3 class="text-success text-center"></h3>
        <SearchHistory></SearchHistory>
      </div>
    </div>
  </div>
</template>

<script>
import TranslateForm from "./components/TranslateForm";
import SearchHistory from "./components/SearchHistory";
export default {
  name: "App",
  components: {
    TranslateForm,
    SearchHistory,
  },
};
</script>

<style>
body {
  background-color: #dedede;
}
</style>