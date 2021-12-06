<template>
  <div>
    <div class="card">
      <div class="card-body">
        <h2 class="mb-5">Belajar Emit 2</h2>

        <h5>Parent: {{ fullname }}</h5>
        <input-type :value="fullname" @get="val => (fullname = val)" />
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      fullname: "Catur Achmadi"
    };
  }
};
</script>
