<template>
  <div>
    <b-navbar toggleable="lg" variant="transparent" id="my-border-nav">
      <div class="container">
        <!-- <b-navbar-brand href="#"></b-navbar-brand> -->
        <router-link class="navbar-brand font-weight-bold" to="/"
          >Covid-19 Visualized</router-link
        >

        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

        <b-collapse id="nav-collapse" is-nav>
          <!-- Right aligned nav items -->
          <b-navbar-nav class="ml-auto">
            <ul class="navbar-nav ml-auto">
              <li class="nav-item">
                <router-link class="nav-link text-dark" to="/">
                  Indonesia
                </router-link>
              </li>
            </ul>
            <ul class="navbar-nav ml-auto">
              <li class="nav-item">
                <router-link class="nav-link text-dark" to="/global">
                  Global
                </router-link>
              </li>
            </ul>
          </b-navbar-nav>
        </b-collapse>
      </div>
    </b-navbar>
  </div>
</template>

<script>
export default {
  name: "Navbar",
};
</script>
