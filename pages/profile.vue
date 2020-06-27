<template>
  <section class="sidebar-layout">
    <b-sidebar
      position="static"
      :mobile="mobile"
      :expand-on-hover="expandOnHover"
      :reduce="reduce"
      type="is-light"
      open
    >
      <div class="p-1">
        <b-menu class="is-custom-mobile">
          <b-menu-list label="Menu">
            <b-menu-item active expanded icon="account" :label="loggedInUser.username">
              <b-menu-item icon="details" label="User Details" />
              <b-menu-item icon="cellphone-link" label="Contact Details" />
              <b-menu-item icon="cash-multiple" label="Payment Details" disabled />
            </b-menu-item>
          </b-menu-list>
          <b-menu-list label="Actions">
            <b-menu-item icon="logout" label="Logout" />
          </b-menu-list>
        </b-menu>
      </div>
    </b-sidebar>
  </section>
</template>

<script>
import { mapGetters } from 'vuex'

export default {
  computed: {
    ...mapGetters(['loggedInUser'])
  },
  middleware: 'auth'
}
</script>
