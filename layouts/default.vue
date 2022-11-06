<template>
  <v-app>
    <v-navigation-drawer v-model="sideDrawer" fixed app>
      <v-list>
        <v-list-item v-for="(item, i) in items" :key="i" :to="item.to" router exact>
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content class="font-display">
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>



    <v-main>
      <v-container fluid> <!--fluid meregangkan container-->
        <Nuxt /> <!--  BAGIAN PENTING! LINE INI BERISI UNTUK MEMANGGIL CONTENT -->
      </v-container>
    </v-main>

    <v-bottom-navigation horizontal height="8vh" fixed color="primary" app>
      <!--  app akan mengikuti ukuran dari browser, ketutup sidebar -->
      <v-app-bar-nav-icon @click.stop="sideDrawer = !sideDrawer" v-ripple="false" plain />
      <v-btn v-for="(item, i) in bottomMenu" :key="i" :to="item.to" v-ripple="false" plain>
        <span class="font-display">{{ item.title }}</span>
        <v-icon>{{ item.icon }}</v-icon>
      </v-btn>
      <v-spacer></v-spacer> <!-- memberi jarak-->
    </v-bottom-navigation>

  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
  data() {
    return {
      sideDrawer: false,
      items: [
        {
          icon: 'mdi-account',
          title: 'Account',
          to: '/account',
        },
        {
          icon: 'mdi-bell',
          title: 'Notification',
          to: '/notification',
        },
      ],
      bottomMenu: [
        {
          icon: 'mdi-application',
          title: 'Welcome',
          to: '/',
        },
      ],
      right: true,
    }
  },
}
</script>
