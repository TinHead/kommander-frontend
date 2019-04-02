<template>
    <v-toolbar header clipped-left>
        <v-toolbar-title class="headline text-uppercase">
        <span>{{ header_name }}</span>
        </v-toolbar-title>
        <v-spacer></v-spacer>
            <v-btn
                flat
                href="https://github.com/vuetifyjs/vuetify/releases/latest"
                target="_blank"
            >
            <span class="mr-2">setup</span>
        </v-btn>
    </v-toolbar>
</template>
<script>
export default {
    data: () => ({
        header_name: 'Kommander'
    })
}
</script>



