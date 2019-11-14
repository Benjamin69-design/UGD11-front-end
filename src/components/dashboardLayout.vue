<template>
    <div>
        <v-navigation-drawer
            v-model="drawer"
            class="grey darken-3"
            dark
            app
            clipped
            fixed
            temporary
            >
                <v-list-item>
                        <v-list-item-content>
                            <v-list-item-title class="title">
                                Modul11
                            </v-list-item-title>
                            <v-list-item-subtitle>
                                Vue Consume REST API
                            </v-list-item-subtitle>
                            </v-list-item-content>
                        </v-list-item>
                        
                        <v-divider></v-divider>
                        <v-list>
                            <v-list-item
                                v-for="item in items"
                                :key="item.title"
                                link
                            >
                            <v-list-item-icon>
                                <v-icon>{{item.icon}}</v-icon>
                            </v-list-item-icon>
                            
                            <v-list-item-content>
                                <router-link :to="{name: item.name}">
                                <v-list-item-title>{{item.title}}</v-list-item-title>
                                </router-link>
                            </v-list-item-content>
                            </v-list-item>
                        </v-list>
                        <template v-slot:append>
                            <div class="pa-2">
                                <v-btn block>Logout</v-btn>
                            </div>
                        </template>
                        </v-navigation-drawer>
                        
                        <v-app-bar
                        dark
                        app
                        fixed
                        clipped-left
                        height="70px"
                        color="grey darken-3">
                        <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
                        <VSpacer/>
                        
                        <img src="../assets/logo.svg" style="height:45px;width:45px">
                        
                        <v-toolbar-title
                            style="font-size:21px;"
                            class="white--text ml-2"
                        >
                        PAW-UAJY
                        </v-toolbar-title>
                        </v-app-bar>

                        <v-content>
                            <router-view />
                        </v-content>
                    </div>
                </template>

<script>
    export default{
        data(){
            return{
                drawer:null,
                items:[
                    {
                        title:'user Controller',icon: 'mdi-human-male' , name: 'UserController'
                    },
                    {
                        title:'vehicles Controller',icon: 'mdi-human-male' , name: 'VehiclesController'
                    },
                ],
            }
        },
    }
</script>