<template>
  <v-app>
    <v-navigation-drawer disable-resize-watcher fixed app :color="$vuetify.theme.themes.dark.primary" dark>
      <v-list>
        <v-list-item
          v-for="(item, i) in sideMenu"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-main>
      <v-container fill-height fluid>
        <Nuxt />
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: "DefaultLayout",
  data() {
    return {
      sideDrawer: false,
      sideMenu: [
        {
          icon: "mdi-view-dashboard-outline",
          title: "Dashboard",
          to: "/",
        },
        {
          icon: "mdi-calendar-month-outline",
          title: "Tahun Ajaran",
          to: "/tahun-ajaran",
        },
        {
          icon: "mdi-account-school-outline",
          title: "Siswa",
          to: "/siswa",
        },
        {
          icon: "mdi-credit-card-outline",
          title: "Pembayaran",
          to: "/pembayaran",
        },
        {
          icon: "mdi-cash-sync",
          title: "Transaksi",
          to: "/transaksi",
        },
        {
          icon: "mdi-receipt-text-outline",
          title: "Tagihan SPP",
          to: "/tagihan-spp",
        },
        {
          icon: "mdi-widgets-outline",
          title: "Komponen",
          to: "/komponen",
        },
        {
          icon: "mdi-list-box-outline",
          title: "Tagihan Lain",
          to: "/tagihan-lain",
        },
      ],
    };
  },
  mounted() {
    this.$router.push("/")
  },
};
</script>
