<template>
  <div class="home">
    <Navbar />
    <div class="container mt-5 mb-5">
      <div class="row">
        <div class="col-md-12 text-center">
          <h3>INDONESIA</h3>
          <!-- <p>Last updatated at: {{ indonesiaCases.update.penambahan.created }}</p> -->
          <hr id="hr-border" />
        </div>
      </div>

      <KumulatifIndonesia :kumulatif="indonesiaCases.update.total" />

      <HarianIndonesia :todayCases="indonesiaCases.update.penambahan" />

      <TableProvinsi :provinsiCases="provinsiCases.list_data" :posts="posts" />

      <TableRumahSakit />
    </div>
    <!-- end of container -->
    <Footer />
  </div>
</template>

<script>
// @ is an alias to /src
import Navbar from "@/components/Navbar.vue";
import KumulatifIndonesia from "@/components/KumulatifIndonesia.vue";
import HarianIndonesia from "@/components/HarianIndonesia.vue";
import TableProvinsi from "@/components/TableProvinsi.vue";
import TableRumahSakit from "@/components/TableRumahSakit.vue";
import Footer from "@/components/layout/Footer.vue";

import axios from "axios";

export default {
  name: "Home",
  components: {
    Navbar,
    KumulatifIndonesia,
    HarianIndonesia,
    TableProvinsi,
    TableRumahSakit,
    Footer,
  },
  data() {
    return {
      indonesiaCases: [],
      provinsiCases: [],
      hospitals: [],
      posts: [
        {
          userId: 1,
          id: 1,
          title: "jaja awo awokaw awokaw jaja",
        },
        {
          userId: 2,
          id: 2,
          title: "Collaboratively promote b",
        },
        {
          userId: 3,
          id: 3,
          title: "lorem ipsum dolor",
        },
        {
          userId: 4,
          id: 4,
          title: "dwidth. Continuall",
        },
        {
          userId: 5,
          id: 5,
          title: "c synergy without world-class manufactured",
        },
      ],
    };
  },
  methods: {
    getIndoCases(data) {
      this.indonesiaCases = data;
    },
    getProvCases(data) {
      this.provinsiCases = data;
    },
    getHospitals(data) {
      this.hospitals = data;
    },
  },
  mounted() {
    // kumulatif
    axios
      .get("https://data.covid19.go.id/public/api/update.json")
      .then((response) => this.getIndoCases(response.data))
      .catch((error) => console.log(error));

    // Provinsi
    axios
      .get("https://data.covid19.go.id/public/api/prov.json")
      .then((response) => this.getProvCases(response.data))
      .catch((error) => console.log(error));
  },
};
</script>
