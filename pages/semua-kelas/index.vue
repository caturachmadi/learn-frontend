<template>
  <div>
    <div class="row">
      <div class="col-md-4" v-for="(item, i) in listClass" :key="i">
        <class-item :name="item.name" :desc="item.desc" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      listClass: [
        { name: "Fullstack 5", desc: "Ini deskripsi Fullstack 5" },
        { name: "Fullstack 6", desc: "Ini deskripsi Fullstack 6" },
        { name: "Fullstack 7", desc: "Ini deskripsi Fullstack 7" },
        { name: "Fullstack 8", desc: "Ini deskripsi Fullstack 8" },
        { name: "Fullstack 9", desc: "Ini deskripsi Fullstack 9" },
        { name: "Fullstack 10", desc: "Ini deskripsi Fullstack 10" }
      ]
    };
  }
};
</script>
