<template>
  <q-page padding class="bg-light">
    <!-- Bagian Hero -->
    <div class="hero-section q-pa-md q-mb-md">
      <q-img src="https://hips.hearstapps.com/hmg-prod.s3.amazonaws.com/images/best-foundation-1519406548.jpg?crop=1.00xw:1.00xh;0,0&resize=1200:*" class="rounded-borders">
        <div class="absolute-bottom bg-black text-white text-center q-pa-md" style="opacity: 0.7;">
        </div>
      </q-img>
    </div>

    <!-- Carousel -->
    <q-carousel v-model="slide" height="600px" arrows infinite animated transition-prev="jump-right" transition-next="jump-left" control-color="pink">
      <q-carousel-slide v-for="(image, index) in images" :key="index" :name="index.toString()">
        <q-img :src="image" class="full-width"></q-img>
        <div class="absolute-bottom bg-black text-white text-center q-pa-sm" style="opacity: 0.5;">
          <h3>Slide {{ index + 1 }}</h3>
        </div>
      </q-carousel-slide>
    </q-carousel>

    <!-- Produk Unggulan -->
    <div class="q-pa-md q-mt-md">
      <h2 class="text-center q-mb-md">Featured product</h2>
      <div class="row justify-center">
        <q-card v-for="(product, index) in products" :key="index" class="my-card q-ma-sm">
          <q-img :src="product.image" class="card-img"></q-img>
          <q-card-section>
            <div class="text-h6">{{ product.name }}</div>
            <div class="text-subtitle1">{{ product.price }}</div>
          </q-card-section>
          <q-card-actions align="right">
            <q-btn flat color="primary" label="Add to chart"></q-btn>
            <q-btn flat color="negative" label="Delete" @click="deleteProduct(index)"></q-btn> <!-- Perubahan di sini -->
          </q-card-actions>
        </q-card>
      </div>
    </div>
  </q-page>
</template>

<script>
export default {
  data() {
    return {
      slide: '0',
      images: [
        'https://www.dior.com/on/demandware.static/-/Library-Sites-DiorSharedLibrary/default/dw3876ca3e/images/beauty/02-MAKEUP/2023/SUMMER-LOOK/SummerLook23_Mood_LipGlow_3000x3000.jpg',
        'https://puls-img.chanel.com/1691070710555-mobile1500x1600pxservicectojpg_1600x1500.jpg',
        'https://thebeautylookbook.com/wp-content/uploads/2023/07/Tom-Ford-Soleil-de-Feu-Summer-Makeup-BEAUTYLOOKBOOK.jpg'
      ],
      products: [
        { name: 'Tom Ford Eyeshadow', price: 'Rp1.000.000', image: 'https://m.media-amazon.com/images/I/71XUN0FQ+rL.jpg' },
        { name: 'Cle de Peau', price: 'Rp950.000', image: 'https://n.nordstrommedia.com/id/sr3/d5cc24dc-853c-469c-88fc-224332a51c3a.jpeg?h=365&w=240&dpr=2' },
        { name: 'Chanel Perfection Lumiere 30 Beige Make Up Foundation [SPF10/30 mL]', price: 'Rp1.500.000', image: 'https://www.static-src.com/wcsstore/Indraprastha/images/catalog/full/bestbuy-world_chanel-perfection-lumiere-long-fluid-make-up-spf10-30-beige-30-ml_full01.jpg' },
        { name: 'MAC Studio Fix Powder Plus Foundation NC 30', price: 'Rp700.000', image: 'https://images.tokopedia.net/img/cache/500-square/product-1/2016/1/16/187264/187264_80629b6b-afba-4645-bb56-d06958a51f3b.jpg' }
      ]
    }
  },
  methods: {
    deleteProduct(index) {
      this.products.splice(index, 1);
    }
  }
}
</script>

<style>
.hero-section {
  background: url('https://via.placeholder.com/1200x400?text=Hero+Section') no-repeat center center;
  background-size: cover;
}

.card-img {
  height: 225px;
  width: 100%;
}

.full-width {
  width: 100%;
}

.my-card {
  width: 250px;
  margin: 10px;
  display: inline-block;
  vertical-align: top;
}

.bg-light {
  background-color: #f9f9f9;
}

.rounded-borders {
  border-radius: 10px;
}
</style>
