<template>

<v-app white>
    <v-navigation-drawer v-model="drawer" clipped app>
        <v-list>
            <v-list-tile v-for="(item, i) in items" :key="i" :to="item.to" router exact>
                <v-list-tile-action>
                    <v-icon>{{ item.icon }}</v-icon>
                </v-list-tile-action>
                <v-list-tile-content>
                    <v-list-tile-title v-text="item.title" />
                </v-list-tile-content>
            </v-list-tile>
        </v-list>
    </v-navigation-drawer>
    <v-toolbar clipped-left app>
        <v-toolbar-side-icon @click="drawer = !drawer" />
        <v-toolbar-title v-text="title" />
    </v-toolbar>
    <v-content>
          <nuxt />
    </v-content>
    <v-footer :fixed="false">
        <span>&copy; 2019</span>
    </v-footer>
</v-app>

</template>

<script>

export default {
    data() {
        return {
            drawer: false,
            items: [{
                icon: 'apps',
                title: 'トップページ',
                to: '/test'
            }, {
                icon: 'bubble_chart',
                title: 'ブログページ',
                to: 'https://rayy-blog.com'
            }],
            title: 'Welcome Question'
        }
    }
}

</script>
