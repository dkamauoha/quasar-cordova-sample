<template>
  <q-page class="column flex-center items-center">
    <q-btn color='primary' size='lg'>
      <router-link to='/status' style='text-decoration: none; color: white;'>Go to Status</router-link>
    </q-btn>
  </q-page>
</template>

<style>
</style>

<script>
export default {
  name: 'PageIndex',
  computed: {
    
  },
  methods: {
    color: function (status) {
      if (status === 'Online') return 'q-mb-none text-positive'
      else if (status === 'Warning') return 'q-b-none text-warning'
      return 'q-b-none text-negative'
    }
  },
  data: function () {
    return {
      items: [
        {
          name: 'Thing1',
          status: 'Online',
          color: 'q-mb-none text-positive',
          icon: 'fas fa-check'
        },
        {
          name: 'Thing2',
          status: 'Warning',
          color: 'q-mb-none text-warning',
          icon: 'fas fa-exclamation-triangle'
        },
        {
          name: 'Thing3',
          status: 'Offline',
          color: 'q-mb-none text-negative',
          icon: 'fas fa-times-circle'
        },
        {
          name: 'Thing4',
          status: 'Online',
          color: 'q-mb-none text-positive',
          icon: 'fas fa-check'
        }
      ]
    }
  }
}
</script>