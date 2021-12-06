<template>
  <div>
    <h4>Belajar Computed</h4>
    <div>
      <ol>
        <li v-for="(book, i) in books" :key="i">{{ book }}</li>
      </ol>
    </div>
    <h5>
      {{ bookLength }}
    </h5>
    <div>
      <h5>Full Name :{{ fullname }}</h5>
      <h5>First Name :{{ firstName }}</h5>
      <h5>Last Name : {{ lastName }}</h5>
      <input class="form-control" type="text" v-model="fullname" />
    </div>
    <!-- <br />
    <br />
    <br />
    <br />
    <h5>
      {{ bookLength }}
    </h5> -->
  </div>
</template>
<script>
export default {
  data() {
    return {
      firstName: "Catur",
      lastName: "Achmadi",
      books: ["Buku Tulis", "Buku Cerita", "Buku Baca", "Novel"]
    };
  },
  computed: {
    fullname: {
      set(value) {
        //         0     1      2
        //value="CATUR ACHMADI"
        const [first, ...lastname] = value.split(" ");
        this.firstName = first;
        this.lastName = lastname.join(" ");
        //    this.firstName = name[0];
        //    this.lastName = name[name.length - 1];
      },
      get() {
        //debugger
        return this.firstName + " " + this.lastName;
      }
    },
    bookLength() {
      return this.books.length > 0
        ? "Bukunya Banyak " + this.books.length
        : "Gak punya Buku";
    }
  }
};
</script>
