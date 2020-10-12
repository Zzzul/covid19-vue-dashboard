<template>
  <div class="harian-indonesia">
    <!-- harian indonesia -->
    <div class="row mt-3">
      <div class="col-md-12">
        <div class="card mt-3" id="my-border">
          <div class="card-header pt-3 pb-0" id="my-border-bot">
            <!-- <b-icon-globe></b-icon-globe> -->
            <p>Informasi Kasus Coronavirus di Indonesia Perhari</p>
          </div>
          <div class="card-body">
            <div class="row">
              <div class="col-md-2">
                <h6 class="card-title mb-1 mb-1">Tanggal</h6>
                <p class="card-text mb-2">
                  {{ todayCases.tanggal }}
                </p>
              </div>

              <div class="col-md-2">
                <h6 class="card-title mb-1">Positif</h6>
                <p class="card-text mb-2">
                  {{ todayCases.jumlah_positif | number("0,0") }}
                </p>
              </div>

              <div class="col-md-2">
                <h6 class="card-title mb-1">Sembuh</h6>
                <p class="card-text mb-2">
                  {{ todayCases.jumlah_sembuh | number("0,0") }}
                </p>
              </div>

              <div class="col-md-2">
                <h6 class="card-title mb-1">Meninggal</h6>
                <p class="card-text mb-2">
                  {{ todayCases.jumlah_meninggal | number("0,0") }}
                </p>
              </div>

              <div class="col-md-2">
                <h6 class="card-title mb-1">Dirawat</h6>
                <p class="card-text mb-2">
                  {{ todayCases.jumlah_dirawat | number("0,0") }}
                </p>
              </div>

              <div class="col-md-2">
                <h6 class="card-title mb-1">Update Terakhir</h6>
                <p class="card-text mb-2">
                  {{ todayCases.created }}
                </p>
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
export default {
  name: "HarianIndonesia",
  props: ["todayCases"],
};
</script>

<style>
</style>