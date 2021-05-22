<template>
  <app-template>
    <template #header>
      <admin-header headerName="Dashboard" />
    </template>

    <admin-dashboard />
  </app-template>
</template>

<script>
import AppTemplate from '@/Layouts/AppTemplate'
import AdminHeader from '@/Parts/Header'
import AdminDashboard from './Components/Main/Dashboard'

export default {
  components: {
    AppTemplate,
    AdminHeader,
    AdminDashboard
  }
}
</script>

<style>

</style>