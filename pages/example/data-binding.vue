<template>
  <div>
    <center>
      <NuxtLink to="/users"> User Nuxt LINK </NuxtLink> ||
      <a href="/users">User A</a>
    </center>
    <br />
    <br />
    <form>
      <div class="form-group">
        <label for="name">Nama</label>
        <input type="text" class="form-control" v-model="name" />
        {{ name }}
      </div>
      <div class="form-group">
        <label for="name">Tanggal lahir</label>
        <input type="date" class="form-control" v-model="date" />
        {{ date }}
      </div>
      <div class="form-group">
        <label for="provinsi">Provinsi</label>
        <select v-model="provinsi" class="form-control">
          <option>-Pilih Provinsi-</option>
          <option
            v-for="(provinsi, i) in listProvinsi"
            :key="i"
            :value="provinsi.name"
            >{{ provinsi.name }}</option
          >
        </select>
        {{ provinsi }}
      </div>
      <p class="h4" v-if="provinsi == 'DKI Jakarta'">AKU BERADA DI JAKARTA</p>
      <p class="h4" v-else-if="provinsi == 'Jawa Tengah'">
        AKU TIDAK BERADA DI JAKARTA
      </p>
      <p class="h4" v-else>AKU KE JAWA TENGAH AJA</p>
      <p v-show="provinsi == 'Jawa tengah'">Hore Aku pergi ke Borobudur</p>
      <!-- <div class="form-group">
        <label for="alamat">Alamat</label>
        <input type="text" class="form-control" v-model="alamat" />
      </div>
      <div class="form-group">
        <label for="deskripsi">Deskripsi</label>
        <input type="text" class="form-control" v-model="deskripsi" />
      </div> -->
      <button class="btn btn-primary">Submit</button>
    </form>

    <hr />
    <div class="form-group">
      <label for="lote">Lotre</label>
      <input type="number" class="form-control" v-model="lotre" />
      {{ lotre }}
    </div>
    <h1 v-if="lotre > 3">{{ lotre * 3 }}</h1>
    <h1 v-else-if="lotre >= 1">{{ lotre * 1 }}</h1>
    <h1 v-if="lotre == 0">KALAH</h1>
  </div>
</template>

<script>
export default {
  data() {
    return {
      lotre: 0,
      name: "Catur",
      date: "",
      provinsi: "DKI Jakarta",
      listProvinsi: [
        { name: "DKI Jakarta" },
        { name: "Jawa Barat" },
        { name: "Jawa Tengah" },
        { name: "Jawa Timur" }
      ]
    };
  }
};
</script>
