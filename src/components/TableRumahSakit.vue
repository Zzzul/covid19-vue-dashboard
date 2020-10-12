<template>
  <!-- table -->
  <div class="row mt-5 mb-5">
    <div class="col-md-12 text-center">
      <h5>Daftar Rumah Sakit Rujukan Covid-19</h5>
    </div>

    <div class="col-md-12 mt-2">
      <div class="table-responsive rounded m-0" id="my-border-no-hover">
        <div class="form-group m-0">
          <input
            type="text"
            class="form-control"
            placeholder="Cari rumah sakit berdasarkan provinsi.."
            id="my-border-bot"
            v-model="search"
          />
        </div>
        <table class="table table-fixed table-striped table-hover table-sm">
          <thead>
            <tr>
              <th scope="col" class="col-1" id="my-border-bot">#</th>
              <th scope="col" class="col-3" id="my-border-bot">Rumah Sakit</th>
              <th scope="col" class="col-2" id="my-border-bot">Provinsi</th>
              <th scope="col" class="col-2" id="my-border-bot">Kota</th>
              <th scope="col" class="col-2" id="my-border-bot">Telepon</th>
              <th scope="col" class="col-2" id="my-border-bot">Alamat</th>
            </tr>
          </thead>
          <tbody>
            <tr
              v-for="(hospital, index) in searchHospital"
              :key="hospital.name"
            >
              <td scope="col" class="col-1">{{ index + 1 }}</td>
              <td scope="col" class="col-3">{{ hospital.name }}</td>
              <td scope="col" class="col-2 pl-3">{{ hospital.province }}</td>
              <td scope="col" class="col-2 pl-3">{{ hospital.region }}</td>
              <td scope="col" class="col-2 pl-3">{{ hospital.phone }}</td>
              <td scope="col" class="col-2 pl-3">{{ hospital.address }}</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>
  <!-- End -->
</template>

<script>
import axios from "axios";
export default {
  name: "TableRumahSakit",
  //   props: ["hospitals"],
  data() {
    return {
      hospitals: [],
      search: "",
    };
  },
  methods: {
    setHospital(data) {
      this.hospitals = data;
    },
  },
  mounted() {
    axios
      .get("https://dekontaminasi.com/api/id/covid19/hospitals")
      .then((response) => this.setHospital(response.data))
      .catch((error) => console.log("Gagal : ", error));
  },
  computed: {
    searchHospital() {
      return this.hospitals.filter((hospital) => {
        return hospital.province
          .toLowerCase()
          .includes(this.search.toLowerCase());
      });
    },
  },
};
</script>

<style>
</style>
