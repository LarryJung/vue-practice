<template>
    <v-toolbar app dark>
        <v-text-field single-line append-icon="search" placeholder="Search" />
        <v-spacer></v-spacer>
        <v-toolbar-items>
            <v-menu v-model="menu" :close-on-content-click="false" :nudge-width="200" offset-x>
                <v-btn icon slot="activator" dark>
                    <v-icon dark>how_to_reg</v-icon>
                </v-btn>
    
                <v-card>
                    <v-list>
                        <v-list-tile avatar>
                            <v-list-tile-avatar>
                                <img src="https://cdn.vuetifyjs.com/images/john.jpg" alt="John">
                            </v-list-tile-avatar>
    
                            <v-list-tile-content>
                                <v-list-tile-title>John Leider</v-list-tile-title>
                                <v-list-tile-sub-title>Founder of Vuetify.js</v-list-tile-sub-title>
                            </v-list-tile-content>
    
                            <v-list-tile-action>
                                <v-btn :class="fav ? 'red--text' : ''" icon @click="fav = !fav">
                                    <v-icon>favorite</v-icon>
                                </v-btn>
                            </v-list-tile-action>
                        </v-list-tile>
                    </v-list>
    
                    <v-divider></v-divider>
    
                    <v-list>
                        <v-list-tile>
                            <v-list-tile-action>
                                <v-switch v-model="message" color="purple"></v-switch>
                            </v-list-tile-action>
                            <v-list-tile-title>Enable messages</v-list-tile-title>
                        </v-list-tile>
    
                        <v-list-tile>
                            <v-list-tile-action>
                                <v-switch v-model="hints" color="purple"></v-switch>
                            </v-list-tile-action>
                            <v-list-tile-title>Enable hints</v-list-tile-title>
                        </v-list-tile>
                    </v-list>
    
                    <v-card-actions>
                        <v-spacer></v-spacer>
    
                        <v-btn flat @click="menu = false">Cancel</v-btn>
                        <v-btn color="primary" flat @click="menu = false">Save</v-btn>
                    </v-card-actions>
                </v-card>
            </v-menu>
            <v-menu>
                <v-toolbar-title slot="activator">
                    <v-btn dark flat round>
                        <v-icon class="px0">language</v-icon>
                        <v-icon class="px0">arrow_drop_down</v-icon>
                    </v-btn>
                </v-toolbar-title>
                <v-list>
                    <v-list-tile v-for="item in items" :key="item" @click="">
                        <v-list-tile-title v-text="item"></v-list-tile-title>
                    </v-list-tile>
                </v-list>
            </v-menu>
    
            <v-btn icon>
                <v-icon>apps</v-icon>
            </v-btn>
    
            <v-btn icon>
                <v-icon>refresh</v-icon>
            </v-btn>
    
            <v-btn icon>
                <v-icon>more_vert</v-icon>
            </v-btn>
        </v-toolbar-items>
    </v-toolbar>
</template>

<script>
    export default {
        data: () => ({
            items: [
                'English', 'Korean', 'German', 'Chinese'
            ],
            fav: true,
            menu: false,
            message: false,
            hints: true
        })
    }
</script>