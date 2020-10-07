<template>
  <div>
    <form @submit.prevent="translateIt" class="well">
      <textarea
        v-model="translateText"
        cols="30"
        rows="5"
        class="form-control"
        placeholder="Çevirmek istediğiniz kelime/cümle yazınız."
      ></textarea>
      <select v-model="translateTo" class="form-control">
        <option></option>
      </select>
      <br />
      <div class="text-left">
        <strong>Tespit Edilen Dil : </strong>
      </div>
      <br />
      <button type="submit" class="btn btn-primary btn-block">
        Çevir Gelsin!
      </button>
    </form>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "TranslateForm",
  data() {
    return {
      translateText: "",
      translateTo: "",
    };
  },
  methods: {
    translateIt() {
      let baseURL =
        "https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20181116T200129Z.775558096056e445.a0cb98993d244e1a93e7aa435b7a0f60a6b5ab4d&text=";
      this.translateText + "&lang=en";
      axios
        .get(baseURL)
        .then((response) => {
          console.log(response);
        })
        .catch((e) => console.log(e));
    },
  },
};
</script>

<style scoped>
</style>