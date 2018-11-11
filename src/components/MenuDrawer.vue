<template>
    <v-card @mouseover="open" @mouseout="fold">
        <v-navigation-drawer v-model="drawer" :mini-variant.sync="mini" app width="250" class="elevation-20">
            <v-toolbar flat class="transparent">
                <v-list class="pa-0">
                    <v-list-tile avatar>
                        <v-list-tile-avatar>
                            <img src="https://randomuser.me/api/portraits/men/85.jpg">
                        </v-list-tile-avatar>
    
                        <v-list-tile-content>
                            <v-list-tile-title>APEX</v-list-tile-title>
                        </v-list-tile-content>
    
                        <v-list-tile-action>
                            <v-btn icon @click.stop="folding">
                                <v-icon>{{foldState}}</v-icon>
                            </v-btn>
                        </v-list-tile-action>
                    </v-list-tile>
                </v-list>
            </v-toolbar>
    
            <v-list v-for="item in items" class="py-0">
                <v-list-tile v-if="!item.items" :key="item.title" @click="">
                    <v-list-tile-action>
                        <v-icon>{{item.action}}</v-icon>
                    </v-list-tile-action>
    
                    <v-list-tile-content>
                        <v-list-tile-title>{{ item.title }}</v-list-tile-title>
                    </v-list-tile-content>
                </v-list-tile>
    
                <v-list-group v-if="item.items" v-model="item.active" :key="item.title" :prepend-icon="item.action" no-action>
                    <v-list-tile slot="activator">
                        <v-list-tile-content>
                            <v-list-tile-title>{{ item.title }}</v-list-tile-title>
                        </v-list-tile-content>
                    </v-list-tile>
    
                    <v-list-tile v-for="subItem in item.items" :key="subItem.title" @click="">
                        <v-list-tile-content>
                            <v-list-tile-title>{{ subItem.title }}</v-list-tile-title>
                        </v-list-tile-content>
                    </v-list-tile>
                </v-list-group>
            </v-list>
        </v-navigation-drawer>
    </v-card>
</template>

<script>
    export default {
        data: () => ({
            drawer: true,
            mini: true,
            foldState: 'toggle_off',
            items: [{
                    action: "chat_bubble_outline",
                    title: "Chat"
                },
                {
                    action: "list_alt",
                    title: "Task Board"
                },
                {
                    action: "queue_music",
                    title: "Player",
                },
                {
                    action: "widgets",
                    title: "Components",
                    items: [{
                        title: "Component-1"
                    },
                    {
                        title: "Component-2"
                        }]
                },
                {
                    action: "healing",
                    title: "Health",
                    items: [{
                        title: "List Item"
                    }]
                },
                {
                    action: "content_cut",
                    title: "Office",
                    items: [{
                        title: "List Item"
                    }]
                },
                {
                    action: "local_offer",
                    title: "Promotions",
                    items: [{
                        title: "List Item"
                    }]
                }
            ],
            right: null
        }),
        methods: {
            open() {
                if (this.foldState === 'toggle_off') {
                    this.mini = false;
                    console.log('open')
                }
    
            },
            fold() {
                if (this.foldState === 'toggle_off') {
                    this.mini = true;
                    console.log('fold')
                }
            },
            folding() {
                if (this.foldState === 'toggle_off') {
                    this.foldState = 'toggle_on'
                } else {
                    this.foldState = 'toggle_off'
                }
            }
    
        }
    };
</script>