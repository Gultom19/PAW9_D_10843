<template>
    <div class="dashboard">
        <v-navigation-drawer class="fullheight" width="256" v-model="drawer"
        absolute temporary color="grey lighten-5">
            <v-list-item>
                <v-list-item-content>
                <v-list-item-title class="title">Daniel Fransiscus Gultom</v-list-item-title>
                <v-list-item-subtitle class="title">200710843</v-list-item-subtitle>
                </v-list-item-content>
            </v-list-item>

            <v-devider></v-devider>

            <v-list dense nav>
                <v-list-item
                    v-for="item in items"
                    :key="item.title"
                    Link
                    color="light-blue darken-4"
                    tag="router-link"
                    :to="item.to">

                    <v-list-item-content>
                        <v-list-item-title>{{item.title}}</v-list-item-title>
                    </v-list-item-content>
                </v-list-item>
            </v-list>
        </v-navigation-drawer>
        <v-app-bar color="red-lighten-3" dark>
            <v-app-bar-nav-icon
            @click="drawer = true"
            color="white"></v-app-bar-nav-icon>
            <VSpacer/>
        </v-app-bar>
        <div class="fullheight pa-5">
            <router-view></router-view>
        </div>
    </div>
</template>
<script>
    export default{
        name: "DashboardIndex",
        data(){
            return{
                drawer: false,
                group: null,
                item: [
                    { title: "Dashboard", to: "/"},
                    { title: "Guided", to:"gd"},
                ],
            };
        },
    };
</script>
<style>
    /* 2 references */
    .fullheight{
        min-height: 100vh !important;
    }
</style>