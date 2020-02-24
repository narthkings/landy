<template>
  <v-app>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
      v-if="this.$vuetify.breakpoint.xsOnly"
      color="deep-purple lighten-5"
    >
      <v-list>
        <v-list-item v-for="(item, i) in items" :key="i" :to="item.to" router exact>
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar class="deep-purple lighten-5" :clipped-left="clipped" fixed app flat>
      <v-row v-if="this.$vuetify.breakpoint.xsOnly">
        <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      </v-row>
      <v-spacer v-if="this.$vuetify.breakpoint.xsOnly" />
      <v-toolbar-title class="ml-4">
        <nuxt-link class="black--text font-weight-bold text-style ml-4" to="/">Bilinguage</nuxt-link>
      </v-toolbar-title>
      <v-spacer v-if="this.$vuetify.breakpoint.smAndUp" />
      <v-toolbar-title
        class="font-weight-medium move-right"
        v-if="this.$vuetify.breakpoint.smAndUp"
      >
        <nuxt-link class="black--text text-style ml-5" to="/">
          <span>
            Courses
            <v-icon right>mdi-chevron-down</v-icon>
          </span>
        </nuxt-link>
        <nuxt-link class="black--text text-style ml-5" to="/why_us">Why us</nuxt-link>
        <nuxt-link class="black--text text-style ml-5" to="/">Support</nuxt-link>

        <v-btn to="/" class="ma-2 round font-weight-bold" rounded outlined color="black">Get Started</v-btn>
      </v-toolbar-title>
    </v-app-bar>
    <v-content class="my-bg white--text">
      <v-container>
        <nuxt />
      </v-container>
    </v-content>

    <v-footer :fixed="fixed" app>
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Courses',
          to: '/'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Why Us',
          to: '/why_us'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Support',
          to: '/Support'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Get Started',
          to: '/started'
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Bilinguage'
    }
  }
}
</script>

<style >
.text-style {
  cursor: pointer;
  text-decoration: none;
}
.round {
  /* border-radius: 3rem; */
  padding: 1.5rem;
}
.move-right {
  margin-right: 4rem;
}
.my-bg {
  background: #9aa1f0;
  /* background: #878bc72f; */
}
</style>