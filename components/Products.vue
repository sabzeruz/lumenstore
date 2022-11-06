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
                    <v-list-item-group v-model="categoryId">
                        <!-- v-list-item v-for="(category, index) in categories" -->
                        <v-list-item v-for="category in categories" :key="category.key"
                        :value="category.id"
                        :disabled="category.id == categoryId"> <!-- Ketika nilai category.id sama dengan categoryId maka akan di disabled  -->
                            <v-list-item-title class="font-display">{{ category.title }}</v-list-item-title>
                        </v-list-item>
                    </v-list-item-group>
                </v-list>
            </v-menu>
        </v-col>

    <v-row>
        <!-- v-col v-for="(product, index) in products"-->
        <v-col v-for="product in filteredProducts" :key="product.key" cols="2"> <!-- fix friendly error -->
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
            categoryId: false,
            categories: [
                {id: false, title: 'All'},
                {id: 1, title: 'Genshin Impact'},
                {id: 2, title: 'Valorant'},
                {id: 3, title: 'Honkai Impact 3'},             
            ],
            products: [
                 { id: 1, title: 'Welkin Moon', thumbnail: 'welkin-moon.png', price: 79000, categoryId: 1 },
                 { id: 2, title: 'x300 Genesis Crystal', thumbnail: '300-genesis.png', price: 79000, categoryId: 1 },
                 { id: 3, title: 'x980 Genesis Crystal', thumbnail: '980-genesis.png', price: 249000, categoryId: 1 },
                 { id: 4, title: 'x1980 Genesis Crystal', thumbnail: '1980-genesis.png', price: 479000, categoryId: 1 },
                 { id: 5, title: 'x3280 Genesis Crystal', thumbnail: '3280-genesis.png', price: 790000, categoryId: 1 },
                 { id: 6, title: 'x6480 Genesis Crystal', thumbnail: '6480-genesis.png', price: 1599000, categoryId: 1 },
                 { id: 1, title: 'x420 Valorant Points', thumbnail: 'valorant-points.png', price: 50000, categoryId: 2 },
                 { id: 2, title: 'x700 Valorant Points', thumbnail: 'valorant-points.png', price: 80000, categoryId: 2 },
                 { id: 3, title: 'x1375 Valorant Points', thumbnail: 'valorant-points.png', price: 150000, categoryId: 2 },
                 { id: 4, title: 'x2400 Valorant Points', thumbnail: 'valorant-points.png', price: 250000, categoryId: 2 },
                 { id: 5, title: 'x4000 Valorant Points', thumbnail: 'valorant-points.png', price: 400000, categoryId: 2 },
                 { id: 6, title: 'x8150 Valorant Points', thumbnail: 'valorant-points.png', price: 800000, categoryId: 2 },
                 { id: 1, title: 'x65 Crystals', thumbnail: 'honkai-crystal.png', price: 79000, categoryId: 3 },
                 { id: 2, title: 'x330 Crystals', thumbnail: 'honkai-crystal.png', price: 79000, categoryId: 3 },
                 { id: 3, title: 'x710 Crystals', thumbnail: 'honkai-crystal.png', price: 249000, categoryId: 3 },
                 { id: 4, title: 'x1430 Crystals', thumbnail: 'honkai-crystal.png', price: 479000, categoryId: 3 },
                 { id: 5, title: 'x3860 Crystals', thumbnail: 'honkai-crystal.png', price: 790000, categoryId: 3 },
                 { id: 6, title: 'x8088 Crystals', thumbnail: 'honkai-crystal.png', price: 1599000, categoryId: 3 },
            ]
        }
    },

    //computed akan langsung menjalankan ketika ada perubahan di data
    computed: {
        filteredProducts() {
            if(this.categoryId){
                return this.products.filter(s => s.categoryId == this.categoryId)
            }

            return this.products
        }
    },

})
</script>


