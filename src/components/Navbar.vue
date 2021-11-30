<template>
<v-app>
    <v-app-bar dense flat app>
        <v-app-bar-nav-icon v-on:click="drawer = !drawer"></v-app-bar-nav-icon>
        <v-app-bar-title>Bismillah App</v-app-bar-title>
        <v-spacer></v-spacer>
        <v-btn text class="warning--text">
            <v-icon left>mdi-lock</v-icon>
            Keluar
        </v-btn>
    </v-app-bar>
    <v-navigation-drawer v-model="drawer" app color="cyan" dark>
        <v-list dense nav>
            <v-list-item-content>
                <v-list-item v-for="item in menuItems" :key="item.name" :to="item.link" active-class="white--text" link>
                    <v-icon left>mdi-account</v-icon>
                    <v-list-item-title>Home</v-list-item-title>
                </v-list-item>
            </v-list-item-content>
        </v-list>
    </v-navigation-drawer>
    <v-main class="grey lighten-4">
        <v-container fluid>
        <router-view></router-view>
        </v-container>
    </v-main>

    <v-footer padless>
        <v-col
        class="text-center"
        cols="12">

        {{ new Date().getFullYear() }} — <strong>Vuetify</strong>
        </v-col>
    </v-footer>
</v-app>
</template>

<script>
export default {
    data:() => ({
        drawer: true,
        menuItems: [
            {icon: 'account', title: 'Home', link: '/'},
            {icon: 'account', title: 'About', link: '/about'},
        ]
    })
}
</script>
