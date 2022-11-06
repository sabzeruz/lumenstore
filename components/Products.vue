<template>
        <v-row>
        <v-col cols="10">
            Search
        </v-col>
        <v-col cols="2">
            <v-menu>
                <!-- Ketika bernilai true, v-list akan terbuka dan sebaliknya  -->
                <template v-slot:activator="{ on: category }"> 
                    <v-btn
                    v-on="category"
                    color="primary"
                    class="font-display"> Category               
                    </v-btn>
                </template>

                <v-list>
                    <v-list-item-group>
                        <v-list-item v-for="(category, index) in categories">
                            <v-list-item-title class="font-display">{{ category.title }}</v-list-item-title>
                        </v-list-item>
                    </v-list-item-group>
                </v-list>
            </v-menu>
        </v-col>

    <v-row>
        <!-- v-col v-for="(product, index) in products"-->
        <v-col v-for="product in products" :key="product.key" cols="2"> <!-- fix friendly error -->
            <v-card :title="product.title"
            :ripple="true">
                <v-card-actions>
                    <v-img :src="require(`@/assets/images/products/${product.thumbnail}`)">
                    </v-img>
                </v-card-actions>
                <v-card-text align="center" class="product-title font-display">
                    {{ product.title }}
                </v-card-text>
            </v-card>
        </v-col>
    </v-row>
    </v-row>
</template>

<script>
// import { defineComponent } from '@vue/composition-api';

export default ({
    data() {
        return {
            categories: [
                {id: 1, title: 'Genshin Impact'},
                {id: 2, title: 'Valorant'},
                {id: 3, title: 'Mobile Legends'},             
            ],
            products: [
                 { id: 1, title: 'Welkin Moon', thumbnail: 'welkin-moon.png', price: 79000, category: 1 },
                 { id: 2, title: 'x300 Genesis Crystal', thumbnail: '300-genesis.png', price: 79000, category: 2 },
                 { id: 3, title: 'x980 Genesis Crystal', thumbnail: '980-genesis.png', price: 249000, category: 2 },
                 { id: 4, title: 'x1980 Genesis Crystal', thumbnail: '1980-genesis.png', price: 479000, category: 2 },
                 { id: 5, title: 'x3280 Genesis Crystal', thumbnail: '3280-genesis.png', price: 790000, category: 2 },
                 { id: 6, title: 'x6480 Genesis Crystal', thumbnail: '6480-genesis.png', price: 1599000, category: 2 },
                 { id: 1, title: 'Welkin Moon', thumbnail: 'welkin-moon.png', price: 79000, category: 1 },
                 { id: 2, title: 'x300 Genesis Crystal', thumbnail: '300-genesis.png', price: 79000, category: 2 },
                 { id: 3, title: 'x980 Genesis Crystal', thumbnail: '980-genesis.png', price: 249000, category: 2 },
                 { id: 4, title: 'x1980 Genesis Crystal', thumbnail: '1980-genesis.png', price: 479000, category: 2 },
                 { id: 5, title: 'x3280 Genesis Crystal', thumbnail: '3280-genesis.png', price: 790000, category: 2 },
                 { id: 6, title: 'x6480 Genesis Crystal', thumbnail: '6480-genesis.png', price: 1599000, category: 2 },
                 { id: 1, title: 'Welkin Moon', thumbnail: 'welkin-moon.png', price: 79000, category: 1 },
                 { id: 2, title: 'x300 Genesis Crystal', thumbnail: '300-genesis.png', price: 79000, category: 2 },
                 { id: 3, title: 'x980 Genesis Crystal', thumbnail: '980-genesis.png', price: 249000, category: 2 },
                 { id: 4, title: 'x1980 Genesis Crystal', thumbnail: '1980-genesis.png', price: 479000, category: 2 },
                 { id: 5, title: 'x3280 Genesis Crystal', thumbnail: '3280-genesis.png', price: 790000, category: 2 },
                 { id: 6, title: 'x6480 Genesis Crystal', thumbnail: '6480-genesis.png', price: 1599000, category: 2 },
                 { id: 1, title: 'Welkin Moon', thumbnail: 'welkin-moon.png', price: 79000, category: 1 },
                 { id: 2, title: 'x300 Genesis Crystal', thumbnail: '300-genesis.png', price: 79000, category: 2 },
                 { id: 3, title: 'x980 Genesis Crystal', thumbnail: '980-genesis.png', price: 249000, category: 2 },
                 { id: 4, title: 'x1980 Genesis Crystal', thumbnail: '1980-genesis.png', price: 479000, category: 2 },
                 { id: 5, title: 'x3280 Genesis Crystal', thumbnail: '3280-genesis.png', price: 790000, category: 2 },
                 { id: 6, title: 'x6480 Genesis Crystal', thumbnail: '6480-genesis.png', price: 1599000, category: 2 },
                 { id: 1, title: 'Welkin Moon', thumbnail: 'welkin-moon.png', price: 79000, category: 1 },
                 { id: 2, title: 'x300 Genesis Crystal', thumbnail: '300-genesis.png', price: 79000, category: 2 },
                 { id: 3, title: 'x980 Genesis Crystal', thumbnail: '980-genesis.png', price: 249000, category: 2 },
                 { id: 4, title: 'x1980 Genesis Crystal', thumbnail: '1980-genesis.png', price: 479000, category: 2 },
                 { id: 5, title: 'x3280 Genesis Crystal', thumbnail: '3280-genesis.png', price: 790000, category: 2 },
                 { id: 6, title: 'x6480 Genesis Crystal', thumbnail: '6480-genesis.png', price: 1599000, category: 2 },
                 { id: 1, title: 'Welkin Moon', thumbnail: 'welkin-moon.png', price: 79000, category: 1 },
                 { id: 2, title: 'x300 Genesis Crystal', thumbnail: '300-genesis.png', price: 79000, category: 2 },
                 { id: 3, title: 'x980 Genesis Crystal', thumbnail: '980-genesis.png', price: 249000, category: 2 },
                 { id: 4, title: 'x1980 Genesis Crystal', thumbnail: '1980-genesis.png', price: 479000, category: 2 },
                 { id: 5, title: 'x3280 Genesis Crystal', thumbnail: '3280-genesis.png', price: 790000, category: 2 },
                 { id: 6, title: 'x6480 Genesis Crystal', thumbnail: '6480-genesis.png', price: 1599000, category: 2 },
            ]
        }
    }
})
</script>


<style scoped>
</style>