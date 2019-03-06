<template>
  <q-page class="column flex-center items-center">
    <h1 v-if='$q.platform.is.mobile'>Status Page</h1>
    <h2 v-if='$q.platform.is.desktop'>Status Page</h2>
    <div v-if='$q.platform.is.mobile' class='q-mb-md'>
      <p class='text-justify'>Mobile <i class="fa fa-wifi"></i></p>
    </div>
    <div v-if='$q.platform.is.desktop' class=''>
      <p>Desktop <i class='fas fa-ethernet'></i></p>
    </div>
    <div class='column flex-center' style='width: 100%;'>
      <q-card v-for='(item, index) in items' :key='index'
        class='row items-center justify-between q-px-md'
        style='width: 80%;'
      >
        <h4>{{ item.name }}</h4>
        <p :class='item.color'>{{ item.status }} <i :class='item.icon'></i></p>
      </q-card>
    </div>
    <q-btn color='primary' size='md' class='q-mt-lg'>
      <router-link to='/' style='text-decoration: none; color: white;'>Back</router-link>
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