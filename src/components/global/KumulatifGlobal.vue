<template>
  <div class="kumulatif-global">
    <!-- kumulatif indonesia-->
    <div class="row mt-4">
      <div class="col-md-4">
        <div
          class="card mb-3 shadow-sm"
          id="my-border"
          style="background-color: #ede682"
        >
          <div class="row no-gutters">
            <div class="col-md-4 p-3 text-center">
              <b-icon-emoji-frown scale="4" class="mt-4"></b-icon-emoji-frown>
            </div>
            <div class="col-md-8">
              <div class="card-body">
                <div class="d-sm-block d-md-none text-center">
                  <h6 class="card-title">Total Positif</h6>
                  <p class="card-text">
                    {{ totalPositif.value }}
                    <!-- {{ 123456 | number('0,0') }}  -->
                  </p>
                </div>

                <div class="d-md-block d-none">
                  <h6 class="card-title">Total Positif</h6>
                  <p class="card-text">
                    {{ totalPositif.value }}
                  </p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <div class="col-md-4">
        <div
          class="card mb-3 shadow-sm"
          id="my-border"
          style="background-color: #ade498"
        >
          <div class="row no-gutters">
            <div class="col-md-4 p-3 text-center">
              <b-icon-emoji-smile scale="4" class="mt-4"></b-icon-emoji-smile>
            </div>
            <div class="col-md-8">
              <div class="card-body">
                <div class="d-sm-block d-md-none text-center">
                  <h6 class="card-title">Total Sembuh</h6>
                  <p class="card-text">
                    {{ totalSembuh.value }}
                  </p>
                </div>

                <div class="d-md-block d-none">
                  <h6 class="card-title">Total Sembuh</h6>
                  <p class="card-text">
                    {{ totalSembuh.value }}
                  </p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <div class="col-md-4">
        <div
          class="card mb-3 shadow-sm"
          id="my-border"
          style="background-color: #f56a79"
        >
          <div class="row no-gutters">
            <div class="col-md-4 p-3 text-center">
              <b-icon-emoji-dizzy scale="4" class="mt-4"></b-icon-emoji-dizzy>
            </div>
            <div class="col-md-8">
              <div class="card-body">
                <div class="d-sm-block d-md-none text-center">
                  <h6 class="card-title">Total Meninggal</h6>
                  <p class="card-text">
                    {{ totalMeninggal.value }}
                  </p>
                </div>

                <div class="d-md-block d-none">
                  <h6 class="card-title">Total Meninggal</h6>
                  <p class="card-text">
                    {{ totalMeninggal.value }}
                  </p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <!-- end of row -->
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "KumulatifGlobal",
  data: () => ({
    totalPositif: [],
    totalSembuh: [],
    totalMeninggal: [],
  }),
  mounted() {
    axios
      .get("https://api.kawalcorona.com/positif")
      .then((response) => (this.totalPositif = response.data))
      .catch((error) => console.log("Gagal : ", error));

    axios
      .get("https://api.kawalcorona.com/sembuh")
      .then((response) => (this.totalSembuh = response.data))
      .catch((error) => console.log("Gagal : ", error));

    axios
      .get("https://api.kawalcorona.com/meninggal")
      .then((response) => (this.totalMeninggal = response.data))
      .catch((error) => console.log("Gagal : ", error));
  },
};
</script>

<style>
</style>