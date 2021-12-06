<template>
  <div>
    <h4>Belajar EMIT</h4>
    <section class="my-5">
      <input-type :value="name" @get="val => (name = val)" />
    </section>
    {{ name }}
    <hr />
    <div class="row">
      <div v-for="(item, i) in listClass" :key="i" class="col-md-4">
        <class-item
          :name="item.name"
          :desc="item.description"
          :img="item.img"
          @follow-class="getValue"
        />
      </div>
    </div>
    <h1 class="mt-3">Following Class</h1>
    <div class="row">
      <div v-for="(item, i) in following" :key="i" class="col-md-4">
        <class-item
          unfollow
          :name="item.name"
          :desc="item.description"
          :img="item.img"
          @unfollow-class="unfollow"
        />
      </div>
    </div>
  </div>
</template>
<script>
export default {
  computed: {
    getListClass() {
      return this.listClass.filter((item, i) => i < 3);
    }
  },
  data() {
    return {
      name: "init",
      following: [],
      listClass: [
        {
          name: "Bootcamp Fullstack 5",
          description: "Kelas Bootstrap paling asik",
          img:
            "https://shiftacademy.id/wp-content/uploads/2020/12/Logo-fullstack-SA.png"
        },
        {
          name: "Mastery Laravel",
          description: "Belajar framework popular php gak pake ribet"
        },
        {
          name: "Mastery Express",
          description: "Belajar framework popular node.js cepat dan ringkas",
          img:
            "https://shiftacademy.id/wp-content/uploads/2021/05/Badge_SA_Class_Alt_2-06-1.png"
        }
      ]
    };
  },
  methods: {
    getValue(data) {
      this.following.push(data);
    },
    unfollow(data) {
      this.following = this.following.filter(
        follow => follow.name != data.name
      );
    }
  }
};
</script>
