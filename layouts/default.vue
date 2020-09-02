<template>
  <div>
    <nav class="navbar py-4">
      <div class="navbar-brand">
        <a class="navbar-item" href="#">
          <img src="~assets/2.png" alt="our logo" width="150" />
        </a>
        <div
          class="navbar-burger burger"
          data-target="navbarExampleTransparentExample"
        >
          <span></span>
          <span></span>
          <span></span>
        </div>
      </div>
      <div
        class="breadcrumb has-large has-angel-right"
        aria-label="breadcrumbs"
      >
        <div class="container py-4">
          <ul>
            <li>
              <a href="#">
                <span class="icon is-small">
                  <b-icon pack="fas" icon="adobe" size="is-large" />
                </span>
                <span><strong>Bulma</strong></span>
              </a>
            </li>
            <li>
              <a href="#">
                <span class="icon is-small">
                  <i class="fas fa-book" aria-hidden="true"></i>
                </span>
                <span><strong>Documentation</strong></span>
              </a>
            </li>
            <li>
              <a href="#">
                <span class="icon is-small">
                  <i class="fas fa-puzzle-piece" aria-hidden="true"></i>
                </span>
                <span><strong>Components</strong></span>
              </a>
            </li>
            <li class="is-active">
              <a href="#">
                <span class="icon is-small">
                  <i class="fas fa-thumbs-up" aria-hidden="true"></i>
                </span>
                <span><strong>Breadcrumb</strong></span>
              </a>
            </li>
          </ul>
        </div>
      </div>
    </nav>
    <!-- ---------------------NAVEND------------------- -->
    <section class="container">
      <div class="column">
        <div class="content">
          <p class="is-size-4"><strong>Belanjaan anda</strong></p>
        </div>
        <div class="columns">
          <div class="column">
            <div class="columns has-text-centered pb-0">
              <div class="column is-2 has-text-grey">Gambar</div>
              <div class="column has-text-grey">Deskripsi</div>
              <div class="column is-1 has-text-grey">Jumlah</div>
              <div class="column is-2 mr-6 has-text-grey has-text-right">
                Harga
              </div>
            </div>
          </div>
          <div class="column is-3"></div>
        </div>
        <div class="columns">
          <div class="column">
            <div class="card-pp" v-for="(item, i) in items" :key="i">
              <div class="columns">
                <div class="column is-2">
                  <figure class="image-figure">
                    <img :src="item.image" alt="" />
                  </figure>
                </div>
                <div class="column">
                  <p>
                    {{ item.title }}
                  </p>
                  <p class="control" v-if="items.rating">
                    <b-rate :value="items.rating" show-score="disabled" />
                  </p>
                  <b-rate
                    v-model="rate"
                    :icon-pack="packs"
                    :icon="icons"
                    :max="maxs"
                    :size="sizes"
                    :locale="locale"
                    :show-score="score"
                    :custom-text="custom"
                    :show-text="text"
                    :texts="texts"
                    :rtl="isRtl"
                    :spaced="isSpaced"
                    :disabled="isDisabled"
                  ></b-rate>
                  <p></p>
                </div>
                <div class="column is-1">
                  <span>
                    <b-dropdown aria-role="list">
                      <button
                        class="button"
                        slot="trigger"
                        slot-scope="{ active }"
                      >
                        <span></span>
                        <b-icon :icon="active ? 'menu-up' : 'menu-down'">
                        </b-icon>
                      </button>
                      <b-dropdown-item aria-role="listitem">1</b-dropdown-item>
                      <b-dropdown-item aria-role="listitem">2</b-dropdown-item>
                      <b-dropdown-item aria-role="listitem">3</b-dropdown-item>
                    </b-dropdown>
                  </span>
                </div>
                <div class="column is-2 mr-6 has-text-right">
                  <p>Rp. 50.000</p>
                </div>
              </div>
              <div class="colums">
                <p>
                  Loreipsum menawi ada yang ditanyakan silahkan akan saya jawab
                  entah itu benar atau salah
                </p>
              </div>
            </div>
          </div>
          <div class="CHECKOUT-PANEL column is-3 px-4 py-4">
            <section class="sidebar">
              <div class="card-py">
                <p class="is-size-4 pb-4"><strong>Ringkasan</strong></p>
                <div class="columns">
                  <div class="column">Total sementara</div>
                  <div class="column has-text-right"><p>Rp. 50.000</p></div>
                </div>
                <div class="columns pb-4">
                  <div class="column">Biaya layanan</div>
                  <div class="column has-text-right">Rp. 5.000</div>
                </div>
                <div class="TEXT-TOTAL columns is-size-5">
                  <div class="column"><b>Total</b></div>
                  <div class="column has-text-right"><b>Rp. 55.000</b></div>
                </div>
                <div class="columns">
                  <div class="column">Durasi pengiriman</div>
                  <div class="column has-text-right">2 hari</div>
                </div>
                <div class="buttons">
                  <b-button type="is-primary" expanded
                    ><strong>Checkout</strong></b-button
                  >
                </div>
              </div>
            </section>
          </div>
        </div>
      </div>
    </section>
    <!-- ------------------------------------------------------ -->
  </div>
</template>

<script>
export default {
  name: 'HomePage',
  data() {
    return {
      rate: 4.6,
      maxs: 5,
      sizes: '',
      packs: 'mdi',
      icons: 'star',
      score: 'true',
      custom: '',
      text: false,
      texts: ['Very bad', 'Bad', 'Good', 'Very good', 'Awesome'],
      isRtl: false,
      isSpaced: false,
      isDisabled: true,
      locale: undefined, // Browser locale
      test: 0,
      items: [
        {
          title:
            'Some reason why my mouth have been silence in one of stopmoment',
          image:
            'https://cdna.artstation.com/p/assets/images/images/010/098/130/large/sajal-kr-chand-flat-landscape.jpg?1522574693',
          rating: 4.4,
        },
        {
          title: 'Slide 1',
          image:
            'https://cdna.artstation.com/p/assets/images/images/010/098/130/large/sajal-kr-chand-flat-landscape.jpg?1522574693',
          rating: 4.4,
        },
        {
          title: 'Slide 1',
          image:
            'https://cdna.artstation.com/p/assets/images/images/010/098/130/large/sajal-kr-chand-flat-landscape.jpg?1522574693',
          rating: 4.4,
        },
        {
          title: 'Slide 1',
          image:
            'https://cdna.artstation.com/p/assets/images/images/010/098/130/large/sajal-kr-chand-flat-landscape.jpg?1522574693',
          rating: 4.4,
        },
        {
          title: 'Slide 1',
          image:
            'https://cdna.artstation.com/p/assets/images/images/010/098/130/large/sajal-kr-chand-flat-landscape.jpg?1522574693',
          rating: 4.4,
        },
      ],
    }
  },
}
</script>
<style>
.sidebar {
  position: sticky;
}
.CHECKOUT-PANEL {
  border-style: solid;
  border-width: thin;
  height: fit-content;
  border-color: lightgrey;
  border-radius: 0.5rem;
}
.TEXT-TOTAL {
  border-top-style: solid;
  border-width: thin;
  border-color: lightgrey;
  border-radius: 0.25rem;
}
</style>
