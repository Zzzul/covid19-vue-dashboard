<template>
  <div class="kumulatif-indonesia">
    <!-- kumulatif indonesia-->
    <div class="row mt-4">
      <div class="col-md-3">
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
                    {{ kumulatif.jumlah_positif | number("0,0") }}
                    <!-- {{ 123456 | number('0,0') }}  -->
                  </p>
                </div>

                <div class="d-md-block d-none">
                  <h6 class="card-title">Total Positif</h6>
                  <p class="card-text">
                    {{ kumulatif.jumlah_positif | number("0,0") }}
                  </p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <div class="col-md-3">
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
                    {{ kumulatif.jumlah_sembuh | number("0,0") }}
                  </p>
                </div>

                <div class="d-md-block d-none">
                  <h6 class="card-title">Total Sembuh</h6>
                  <p class="card-text">
                    {{ kumulatif.jumlah_sembuh | number("0,0") }}
                  </p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <div class="col-md-3">
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
                    {{ kumulatif.jumlah_meninggal | number("0,0") }}
                  </p>
                </div>

                <div class="d-md-block d-none">
                  <h6 class="card-title">Total Meninggal</h6>
                  <p class="card-text">
                    {{ kumulatif.jumlah_meninggal | number("0,0") }}
                  </p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <div class="col-md-3">
        <div
          class="card mb-3 shadow-sm"
          id="my-border"
          style="background-color: #ddf3f5"
        >
          <div class="row no-gutters">
            <div class="col-md-4 p-3 text-center">
              <b-icon-building scale="4" class="mt-4"></b-icon-building>
            </div>
            <div class="col-md-8">
              <div class="card-body">
                <div class="d-sm-block d-md-none text-center">
                  <h6 class="card-title">Total Dirawat</h6>
                  <p class="card-text">
                    {{ kumulatif.jumlah_dirawat | number("0,0") }}
                  </p>
                </div>

                <div class="d-md-block d-none">
                  <h6 class="card-title">Total Dirawat</h6>
                  <p class="card-text">
                    {{ kumulatif.jumlah_dirawat | number("0,0") }}
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
export default {
  name: "KumulatifIndonesia",
  props: ["kumulatif"],
};
</script>

<style></style>
