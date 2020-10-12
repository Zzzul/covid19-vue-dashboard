<template>
  <div class="global">
    <Navbar />
    <div class="container mt-5">
      <div class="row">
        <div class="col-md-12 text-center">
          <h3>GLOBAL</h3>
          <!-- <p>Last updatated at: {{ indonesiaCases.update.penambahan.created }}</p> -->
          <hr id="hr-border" />
        </div>
      </div>

      <KumulatifGlobal />

      <TableGlobal />
    </div>

    <Footer />
  </div>
</template>

<script>
import Navbar from "@/components/Navbar.vue";
import KumulatifGlobal from "@/components/global/KumulatifGlobal.vue";
import TableGlobal from "@/components/global/TableGlobal.vue";
import Footer from "@/components/layout/Footer.vue";

export default {
  name: "Global",
  components: {
    Navbar,
    KumulatifGlobal,
    TableGlobal,
    Footer,
  },
};
</script>

<style></style>
