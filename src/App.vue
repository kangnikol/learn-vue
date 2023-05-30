<template>
  <Suspense #default>
    <Users />
  </Suspense>
  <Suspense #fallback>
    Loading . . .
  </Suspense>
</template>
<script>
import Users from './components/Users.vue'
export default {
  components: { Users }
}
</script>
<style></style>