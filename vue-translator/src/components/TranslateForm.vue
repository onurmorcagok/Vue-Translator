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
            "https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20170329T180255Z.3c18d2dc7b65d525.f23ed9a9efa992bded4ef96334e3c154f61d2dea&lang=en'+language+'&text="
            this.translateText;
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