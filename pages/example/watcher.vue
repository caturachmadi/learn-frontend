<template>
  <div>
    <h4>Belajar Watcher</h4>
    <input type="text" class="form-control" v-model="question" />
    <h4>{{ answer }}</h4>
    <img :src="img" class="w-100" alt="" srcset="" />
  </div>
</template>
<script>
export default {
  data() {
    return {
      img: "",
      question: "",
      answer: "Opo tah?"
    };
  },
  watch: {
    question(newValue, oldValue) {
      if (newValue.indexOf("?") > -1) {
        this.getAnswer;
      }
    }
  },
  methods: {
    getAnswer() {
      this.answer = "Sedang berfikir";
      this.$axios.$get("https://yesno.wtf/api").then(response => {
        console.log(response);
        this.answer = response.answer;
        this.img = response.image;
      });
    }
  }
};
</script>
