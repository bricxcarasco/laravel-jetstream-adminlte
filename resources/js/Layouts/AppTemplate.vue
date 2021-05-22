<template>
  <div class="dark-mode">
    <div class="wrapper">
      <admin-navbar />

      <admin-sidebar />

      <div class="content-wrapper">
        <div class="content-header">
          <slot name="header"></slot>
        </div>

        <section class="content">
          <slot></slot>
        </section>
      </div>

      <admin-footer />
    </div>
  </div>
</template>

<script>
import AdminNavbar from '@/Parts/Navbar'
import AdminSidebar from '@/Parts/Sidebar'
import AdminFooter from '@/Parts/Footer'

export default {
  components: {
    AdminNavbar,
    AdminSidebar,
    AdminFooter
  },
  
  data() {
    return {
      showingNavigationDropdown: false,
    }
  },

  methods: {
    switchToTeam(team) {
      this.$inertia.put(route('current-team.update'), {
        'team_id': team.id
      }, {
        preserveState: false
      })
    },

    logout() {
      this.$inertia.post(route('logout'));
    },
  },

  computed: {
    path() {
      return window.location.pathname
    }
  }
}
</script>
