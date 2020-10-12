<template>
  <div class="table-provinsi">
    <!-- table -->
    <div class="row mt-5">
      <div class="col-md-12 text-center">
        <h5>Daftar Kasus Covid-19 Berdasarkan Provinsi</h5>
      </div>
      <div class="col-md-12">
        <div class="table-responsive rounded m-0" id="my-border-no-hover">
          <div class="form-group m-0">
            <input
              type="text"
              class="form-control"
              placeholder="Cari kasus covid-19 berdasarkan provinsi.."
              id="my-border-bot"
              v-model="filter"
            />
          </div>
          <table class="table table-fixed table-striped table-hover table-sm">
            <thead>
              <tr>
                <th scope="col" class="col-1" id="my-border-bot">#</th>
                <th scope="col" class="col-3" id="my-border-bot">Provinsi</th>
                <th scope="col" class="col-2" id="my-border-bot">Positif</th>
                <th scope="col" class="col-2" id="my-border-bot">Sembuh</th>
                <th scope="col" class="col-2" id="my-border-bot">Meninggal</th>
                <th scope="col" class="col-2" id="my-border-bot">Dirawat</th>
              </tr>
            </thead>
            <tbody>
              <tr v-for="(prov, index) in provinsiCases" :key="prov.key">
                <td scope="col" class="col-1">{{ index + 1 }}</td>
                <td scope="col" class="col-3">{{ prov.key }}</td>
                <td scope="col" class="col-2 pl-3">
                  {{ prov.jumlah_kasus | number("0,0") }}
                </td>
                <td scope="col" class="col-2 pl-3">
                  {{ prov.jumlah_sembuh | number("0,0") }}
                </td>
                <td scope="col" class="col-2 pl-3">
                  {{ prov.jumlah_meninggal | number("0,0") }}
                </td>
                <td scope="col" class="col-2 pl-4">
                  {{ prov.jumlah_dirawat | number("0,0") }}
                </td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </div>
    <!-- End -->

    <!-- <div class="row">
      <div class="col-md-12">
        <b-row>
          <b-col md="3">
            <b-form-input
              v-model="filter"
              type="search"
              placeholder="Search"
              class="mb-3 mt-4"
            ></b-form-input>
          </b-col>
        </b-row>
        <b-row>
          <b-col class="rounded">
            <b-table
              striped
              hover
              small
              :items="posts"
              :filter="filter"
              :per-page="perPage"
              :current-page="currentPage"
              :fields="fields"
              :fixed="true"
              id="my-border-no-hover"
            >
              <template v-slot:cell(actions)="data">
                <b-button variant="danger" @click="deleteItem(data.item.id)"
                  >Delete</b-button
                >
              </template>
            </b-table>
            <b-pagination
              v-model="currentPage"
              :total-rows="rows"
              :per-page="perPage"
            ></b-pagination>
          </b-col>
        </b-row>
      </div>
    </div> -->
  </div>
</template>

<script>
export default {
  name: "TableProvinsi",
  props: ["provinsiCases", "posts"],
  data: () => ({
    perPage: 2,
    currentPage: 1,
    filter: "",
    fields: [
      {
        key: "userId",
        sortable: true,
        label: "User ID",
      },
      {
        key: "id",
        sortable: true,
      },
      {
        key: "title",
        sortable: true,
      },
      {
        key: "actions",
        sortable: false,
      },
    ],
  }),
  computed: {
    rows() {
      return this.posts.length;
    },
  },
  methods: {
    deleteItem(id) {
      const index = this.posts.indexOf((x) => x.id === id);
      this.posts.splice(index, 1);
    },
  },
};
</script>

<style></style>
