<template>
  <v-container>
    <v-row>
      <v-col>
        <h1>Oops!</h1>
        <BrokenLink />
        <router-link to="/">Back to the home page</router-link>
      </v-col>
    </v-row>
    <script type="application/javascript">
      // ========================================
      // Credits:
      // - https://stackoverflow.com/a/50259501
      // - https://stackoverflow.com/a/50247140
      // ========================================
      const segment = 1

      sessionStorage.redirect =
        '/' +
        location.pathname
          .slice(1)
          .split('/')
          .slice(segment)
          .join('/')

      location.replace(
        location.pathname
          .split('/')
          .slice(0, 1 + segment)
          .join('/'),
      )
    </script>
  </v-container>
</template>

<script>
import BrokenLink from '@/components/BrokenLink'

export default {
  name: 'NotFound',
  components: {
    BrokenLink,
  },
}
</script>
