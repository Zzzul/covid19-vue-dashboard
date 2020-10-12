<template>
  <div class="table-global">
    <!-- table -->
    <div class="row mt-5 mb-4">
      <div class="col-md-12 text-center">
        <h5>Daftar Kasus Covid-19 di Seluruh Dunia</h5>
      </div>

      <div class="col-md-12 mt-2">
        <div class="table-responsive rounded m-0" id="my-border-no-hover">
          <div class="form-group m-0">
            <input
              type="text"
              class="form-control"
              placeholder="Cari berdasarkan negara.."
              id="my-border-bot"
              v-model="search"
            />
          </div>
          <table class="table table-fixed table-striped table-hover table-sm">
            <thead>
              <tr>
                <th scope="col" class="col-1" id="my-border-bot">#</th>
                <th scope="col" class="col-3" id="my-border-bot">Negara</th>
                <th scope="col" class="col-2" id="my-border-bot">Positif</th>
                <th scope="col" class="col-2" id="my-border-bot">Sembuh</th>
                <th scope="col" class="col-2" id="my-border-bot">Meninggal</th>
                <th scope="col" class="col-2" id="my-border-bot">Dirawat</th>
              </tr>
            </thead>
            <tbody>
              <tr v-for="(glob, index) in searchCountry" :key="glob.OBJECTID">
                <td scope="col" class="col-1">{{ index + 1 }}</td>
                <td scope="col" class="col-3">
                  {{ glob.attributes.Country_Region }}
                </td>
                <td scope="col" class="col-2 pl-2">
                  {{ glob.attributes.Confirmed | number("0,0") }}
                </td>
                <td scope="col" class="col-2 pl-3">
                  {{ glob.attributes.Recovered | number("0,0") }}
                </td>
                <td scope="col" class="col-2 pl-3">
                  {{ glob.attributes.Deaths | number("0,0") }}
                </td>
                <td scope="col" class="col-2 pl-3">
                  &nbsp;&nbsp;&nbsp;&nbsp;
                  {{ glob.attributes.Active | number("0,0") }}
                </td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </div>
    <!-- End -->
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "TableGlobal",
  data: () => ({
    global: [],
    search: "",
  }),
  mounted() {
    axios
      .get("https://api.kawalcorona.com/")
      .then((response) => (this.global = response.data))
      .catch((error) => console.log("Gagal : ", error));
  },
  computed: {
    searchCountry() {
      return this.global.filter((glob) => {
        return glob.attributes.Country_Region.toLowerCase().includes(
          this.search.toLowerCase()
        );
      });
    },
  },
};
</script>

<style>
</style>