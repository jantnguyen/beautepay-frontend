<template lang="pug">
  v-app-bar(app dark color="primary")
    v-app-bar-nav-icon(  rounded @click.stop="$emit('drawerClick')")
    v-toolbar-title(style="fontSize:150%") Beaute'-Pay
    v-spacer
    v-btn( outlined to="/" text  color="light" style="text-transform: capitalize; margin-right:5px;") Home
    v-btn( outlined  to="/about" text  color="light" style="text-transform: capitalize; margin-right:5px;") About
    template(v-if="orgs && orgs.length")
      template(v-if="orgs.length > 1")
        v-btn( outlined  to="/orgs" text  color="light" style="text-transform: capitalize; margin-right:5px;") Features
      template(v-else)
        v-btn( outlined  :to="{ path: 'orgs', name: 'Organization', params: { orgId: orgs[0].slug }}" text color="light" style="text-transform: capitalize; margin-right:5px;") Interfaces
    v-btn( outlined  text  color="light" @click="login" style="text-transform: capitalize; margin-right:5px;") Login
</template>

<script>
export default {
  props: {
    orgs: Array
  },
  methods: {
    login () {
      window.location.href = '/api/auth/login'
    }
  }
}
</script>
