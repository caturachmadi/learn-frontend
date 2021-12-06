<template>
  <div>
    <h4>Belajar method</h4>
    <div class="text-center">
      <h4>{{ count }}</h4>
    </div>
    <items-button @click.native="counter(12)" />
  </div>
</template>
<script>
export default {
  data() {
    return {
      count: 0,
      name: "Catur A"
    };
  },
  methods: {
    counter(val) {
      this.count += val;
      this.name;
      this.decrement();
    },
    decrement() {
      setTimeout(() => {
        this.count -= 7;
      }, 500);
    }
  }
};
</script>
