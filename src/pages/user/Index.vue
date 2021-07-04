<template>
    <q-page padding>
      <div class="q-pa-md"/>
    <q-carousel
      animated
      v-model="slide"
      navigation
      infinite
      autoplay
      arrows
      swipeable
      transition-prev="slide-right"
      transition-next="slide-left"
    >
      <q-carousel-slide :name="1" img-src="https://danieldokter.files.wordpress.com/2013/08/cl4.jpg" />
      <q-carousel-slide :name="2" img-src="data:image/jpeg;base64,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" />
      <q-carousel-slide :name="3" img-src="https://cdn.quasar.dev/img/parallax2.jpg" />
      <q-carousel-slide :name="4" img-src="https://cdn.quasar.dev/img/quasar.jpg" />
    </q-carousel>
    <div class="row q-pa-md">
        <div class="col-md-3 col-xs-12" v-for="(movie, i) in data" :key="i">
         <q-card>

      <q-img
        :src="`${$baseImageURL}/${movie.image}`"
        :ratio="16/9"
      />
      <q-card-section>
        <q-btn
          fab
          color="red"
          icon="add_shopping_cart"
          class="absolute"
          unelevated
          style="top: 0; right: 12px; transform: translateY(-50%);"
        />

        <div class="row no-wrap items-center">
          <div class="col text-h6 ellipsis">
            {{ movie.judulFilm }}
          </div>
        </div>

        <q-rating v-model="movie.rating" readonly :max="5" size="32px" />
      </q-card-section>

      <q-card-section class="q-pt-none">
        <div class="text-subtitle1">
          {{ movie.genre }}
        </div>
        <div class="text-subtitle1">
          Rp. {{ movie.harga }},-
        </div>
        <div @click="movie.expanded = !movie.expanded" class="text-caption text-grey cursor-pointer">
          Tampilkan Deskripsi
        </div>
        <q-slide-transition>
          <div v-show="movie.expanded">
            <div class="text-grey text-caption">
              {{ movie.deskripsi }}
            </div>
          </div>
        </q-slide-transition>
      </q-card-section>

      <q-card-actions>
        <q-btn unelevated @click="openDetail(movie)" class="full-width" color="primary">
          Order Now
        </q-btn>
      </q-card-actions>
    </q-card>
        </div>
    </div>
    <q-dialog v-model="dialog" v-if="dialog" position="bottom">
      <q-card style="width: 500px">
        <q-card-section>
            <div class="text-h6">Detail Pemesanan</div>
        </q-card-section>
        <q-card-section style="max-height: 50vh" class="scroll">
          {{ activeData.judulFilm }} - {{ activeData.harga }}
        <q-form class="q-mt-md">
            <q-input filled type="number" v-model="jumlah" label= "Masukan Jumlah"/>
            Rp. {{ total }},-
             <q-file color="teal" class="q-mt-md" filled v-model="image" label="Label">
        <template v-slot:prepend>
          <q-icon name="cloud_upload" />
        </template>
      </q-file>
        </q-form>
        </q-card-section>
        <q-card-actions align="right">
            <q-btn flat label="Batal" v-close-popup/>
            <q-btn color="black" @click="prosesTransaksi" label="Proses"  />
        </q-card-actions>
      </q-card>
    </q-dialog>

    </q-page>
</template>
<script>
export default {
  data () {
    return {
      stars: 4,
      slide: 1,
      dialog: false,
      image: null,
      data: [],
      activeData: null,
      jumlah: 1
    }
  },
  created () {
    this.getData()
  },
  methods: {
    getData () {
      this.$axios.get('movie/getall')
        .then(res => {
          if (res.data.sukses) {
            this.data = res.data.data.map(movie => {
              return Object.assign(movie, {
                expanded: false
              })
            })
          } else {
            this.$showNotif(res.data.pesan, 'negative')
          }
        })
    },
    openDetail (data) {
      this.activeData = data
      this.dialog = true
    },
    prosesTransaksi () {
      const formData = new FormData()
      formData.append('image', this.image)
      formData.append('data', JSON.stringify({
        idUser: this.$q.localStorage.getItem('dataUser')._id,
        idFilm: this.activeData._id,
        harga: this.activeData.harga,
        jumlah: this.jumlah,
        total: this.total
      }))
      this.$axios.post('order/insert', formData)
        .then(res => {
          if (res.data.sukses) {
            this.$showNotif(res.data.pesan, 'positive')
            this.dialog = false
            this.image = null
          } else {
            this.$showNotif(res.data.pesan, 'negative')
          }
        })
    }
  },
  computed: {
    total () {
      return this.activeData.harga * this.jumlah
    }
  }
}
</script>
