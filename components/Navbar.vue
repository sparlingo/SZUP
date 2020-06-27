<template>
  <b-navbar fixed-top shadow type="is-info">
    <template slot="brand">
      <b-navbar-item tag="router-link" :to="{ path: '/' }">
        <img
          src="../static/shenzhen.png"
          alt="Shenzhen Ultimate Frisbee"
        >
      </b-navbar-item>
    </template>
    <template slot="start">
      <b-navbar-item href="/">
        Home
      </b-navbar-item>
      <b-navbar-item href="whatisultimate">
        What is Ultimate?
      </b-navbar-item>
      <b-navbar-item>
        League
      </b-navbar-item>
      <b-navbar-item>
        Photos
      </b-navbar-item>
      <b-navbar-item href="fields">
        Fields
      </b-navbar-item>
      <b-navbar-dropdown label="Info">
        <b-navbar-item href="#">
          About
        </b-navbar-item>
        <b-navbar-item href="#">
          Contact
        </b-navbar-item>
      </b-navbar-dropdown>
    </template>

    <template slot="end">
      <b-navbar-item tag="div">
        <div v-if="isAuthenticated" class="navbar-item has-dropdown is-hoverable">
          <b-navbar-dropdown :label="loggedInUser.username">
            <b-navbar-item href="/profile">
              My Profile
            </b-navbar-item>
            <hr class="navbar-divider">
            <b-navbar-item @click="logout">
              Logout
            </b-navbar-item>
          </b-navbar-dropdown>
        </div>
        <div v-else class="buttons">
          <a class="button is-dark" href="register">
            <strong>Sign up</strong>
          </a>
          <a class="button is-light" href="login">
            Log in
          </a>
        </div>
      </b-navbar-item>
    </template>
  </b-navbar>
</template>

<style scoped>
</style>

<script>
import { mapGetters } from 'vuex'

export default {
  computed: {
    ...mapGetters(['isAuthenticated', 'loggedInUser'])
  },
  methods: {
    async logout () {
      await this.$auth.logout()
    }
  }
}
</script>
