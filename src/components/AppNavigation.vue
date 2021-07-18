<template>
    <span>
        <v-navigation-drawer
            app
            v-model="drawer"
            class="brown lighten-2"
            dark
            disable-resize-watcher
        >
            <v-list>
                <template v-for="(item, index) in items">
                    <v-list-tile :key="index">
                        <v-list-tile-content>
                            {{ item.title }}
                        </v-list-tile-content>
                    </v-list-tile>
                    <v-divider :key="`divider-${index}`"></v-divider>
                </template>
            </v-list>
        </v-navigation-drawer>
        <v-toolbar app color="brown darken-4" dark>
            <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
            <v-spacer class="d-flex d-md-none"></v-spacer>
            <v-toolbar-title>{{ appTitle }}</v-toolbar-title>
            <v-btn flat class="d-none d-md-flex">Menu</v-btn>
            <v-spacer class="d-none d-md-flex"></v-spacer>
            <v-btn flat class="d-none d-md-flex">SIGN IN</v-btn>
            <v-btn color="brown lighten-3" class="d-none d-md-flex">
                JOIN
            </v-btn>
        </v-toolbar>
    </span>
</template>

<script>
export default {
    name: 'AppNavigation',
    data() {
        return {
            appTitle: 'Meal Prep',
            drawer: false,
            items: [{ title: 'Menu' }, { title: 'Sign In' }, { title: 'Join' }],
        };
    },
};
</script>

<style scoped></style>
