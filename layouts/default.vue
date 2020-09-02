<template>
  <div>
    <nav class="navbar py-4">
      <div class="LOGO navbar-brand px-2">
        <a class="navbar-item" href="#">
          <img
            src="~assets/2.png"
            alt="Bulma: a modern CSS framework based on Flexbox"
            width="150"
          />
        </a>
      </div>
      <div
        class="BREADCRUMB breadcrumb is-medium py-4 is-size-6 has-text-weight-semibold"
        aria-label="breadcrumbs"
      >
        <div>
          <ul>
            <li>
              <a class="has-text-dark" href="#">
                <span>
                  <img
                    src="https://img.icons8.com/metro/26/000000/card-in-use.png"
                  />
                </span>
                <span>Basket</span>
              </a>
            </li>
            <li>
              <a class="has-text-dark" href="#">
                <span>
                  <img
                    src="https://img.icons8.com/metro/26/000000/card-in-use.png"
                  />
                </span>
                <span>Shopping</span>
              </a>
            </li>
            <li>
              <a class="has-text-dark" href="#">
                <span>
                  <img
                    src="https://img.icons8.com/metro/26/000000/card-in-use.png"
                  />
                </span>
                <span>Payment</span>
              </a>
            </li>
            <li class="is-active">
              <a class="has-text-dark" href="#">
                <span>
                  <img
                    src="https://img.icons8.com/metro/26/000000/card-in-use.png"
                  />
                </span>
                <span>Shipping</span>
              </a>
            </li>
          </ul>
        </div>
      </div>
    </nav>
    <!-- ---------------------NAVEND------------------- -->
    <section class="container">
      <div class="column">
        <div class="container mb-4">
          <p class="is-size-3"><strong>Pesanan Anda</strong></p>
        </div>
        <div class="columns">
          <div class="column mr-5">
            <div class="BORDER-TOP columns has-text-centered pb-0 mb-0">
              <div class="column is-2 has-text-grey-light py-0">
                Gambar
              </div>
              <div class="column has-text-grey-light py-0">
                Deskripsi
              </div>
              <div class="column is-2 has-text-grey-light py-0">
                Jumlah
              </div>
              <div class="column is-2 has-text-grey-light py-0">
                Harga
              </div>
            </div>
          </div>
          <div class="column is-3"></div>
        </div>
        <div class="columns">
          <div class="column mr-5">
            <div class="card-pp" v-for="(item, i) in items" :key="i">
              <div class="columns">
                <div class="column is-2">
                  <figure class="image">
                    <img :src="item.image" alt="" />
                  </figure>
                </div>
                <div class="column">
                  <p class="is-size-6 has-text-weight-semibold">
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
                    class="mt-1 mb-1"
                  ></b-rate>
                  <p></p>
                </div>
                <div class="JUMLAH column is-2 has-text-centered">
                  <b-dropdown v-model="is1" aria-role="list">
                    <button class="button" type="button" slot="trigger">
                      <template v-if="is1">
                        <span>1</span>
                      </template>
                      <template v-else-if="is2">
                        <span>2</span>
                      </template>
                      <template v-else-if="is3">
                        <span>3</span>
                      </template>
                      <template v-else-if="is4">
                        <span>4</span>
                      </template>
                      <template v-else>
                        <span>5</span>
                      </template>
                      <b-icon icon="menu-down"></b-icon>
                    </button>

                    <b-dropdown-item :value="true" aria-role="listitem">
                      <div class="media">
                        <div class="media-content">
                          <h6>1</h6>
                        </div>
                      </div>
                    </b-dropdown-item>

                    <b-dropdown-item :value="false" aria-role="listitem">
                      <div class="media">
                        <div class="media-content">
                          <h6>2</h6>
                        </div>
                      </div>
                    </b-dropdown-item>

                    <b-dropdown-item :value="false" aria-role="listitem">
                      <div class="media">
                        <div class="media-content">
                          <h6>3</h6>
                        </div>
                      </div>
                    </b-dropdown-item>

                    <b-dropdown-item :value="false" aria-role="listitem">
                      <div class="media">
                        <div class="media-content">
                          <h6>4</h6>
                        </div>
                      </div>
                    </b-dropdown-item>

                    <b-dropdown-item :value="false" aria-role="listitem">
                      <div class="media">
                        <div class="media-content">
                          <h6>5</h6>
                        </div>
                      </div>
                    </b-dropdown-item>
                  </b-dropdown>
                </div>
                <div class="column is-2 has-text-right">
                  <p>Rp. 50.000</p>
                </div>
              </div>
              <div class="container">
                <div class="RINCIAN is-size-6 has-text-right">
                  <a class="has-text-halo" href="">Rincian paket</a>
                </div>
                <div class="RINCIAN-PAKET container pb-3">
                  <div class="container is-size-5 mb-5">
                    <strong>PREMIUM</strong>
                  </div>
                  <div
                    class="container is-size-7 has-text-grey has-text-weight-normal"
                  >
                    <ul class="LIST columns is-multiline">
                      <li class="column is-one-quarter py-0">
                        <b-icon
                          icon="check"
                          type="is-success"
                          size="is-small"
                        ></b-icon>
                        <span>Fasilitas 1</span>
                      </li>
                      <li class="column is-one-quarter py-0">
                        <b-icon
                          icon="check"
                          type="is-success"
                          size="is-small"
                        ></b-icon>
                        <span>Fasilitas 2</span>
                      </li>
                      <li class="column is-one-quarter py-0">
                        <b-icon
                          icon="check"
                          type="is-success"
                          size="is-small"
                        ></b-icon>
                        <span>Fasilitas 3</span>
                      </li>
                      <li class="column is-one-quarter py-0">
                        <b-icon
                          icon="check"
                          type="is-success"
                          size="is-small"
                        ></b-icon>
                        <span>Fasilitas 4</span>
                      </li>
                      <li class="column is-one-quarter py-0">
                        <b-icon
                          icon="check"
                          type="is-success"
                          size="is-small"
                        ></b-icon>
                        <span>Fasilitas 5</span>
                      </li>
                      <li class="column is-one-quarter py-0">
                        <b-icon
                          icon="check"
                          type="is-success"
                          size="is-small"
                        ></b-icon>
                        <span>Fasilitas 6</span>
                      </li>
                      <li class="column is-one-quarter py-0">
                        <b-icon
                          icon="check"
                          type="is-success"
                          size="is-small"
                        ></b-icon>
                        <span>Fasilitas 7</span>
                      </li>
                    </ul>
                  </div>
                </div>
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
                  <div class="column">Durasi layanan (Hari)</div>
                  <div class="column is-one-third has-text-right">2 Hari</div>
                </div>
                <div class="TEXT-TOTAL columns is-size-5">
                  <div class="column"><b>Total</b></div>
                  <div class="column has-text-right">
                    <b>Rp. 100.000</b>
                  </div>
                </div>
                <div class="buttons">
                  <b-button type="is-halo" expanded
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
      sizes: 'is-small',
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
      ],
      is1: true,
      is2: true,
      is3: true,
      is4: true,
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
  border-radius: 0.25rem;
}
.TEXT-TOTAL {
  border-top-style: solid;
  border-width: thin;
  border-color: lightgrey;
  border-radius: 0.25rem;
}
.BORDER-TOP {
  border-top-style: solid;
  border-width: thin;
  border-color: lightgrey;
}
a.dropdown-item.is-active,
.dropdown .dropdown-menu .has-link a.is-active,
button.dropdown-item.is-active {
  /* background-color: #7957d5; */
  /* color: #fff; */
}
.button.is-halo {
  border-color: transparent;
  background-color: #f79351;
  color: #fff;
}
.has-text-halo {
  color: #f79351 !important;
}
.RINCIAN-PAKET {
  border-bottom-style: solid;
  border-width: thin;
  border-color: lightgrey;
}
.JUMLAH.button {
  padding-left: 1em;
  padding-right: 1em;
}
.LIST {
  max-height: 150px;
  line-height: 3rem;
}
.LIST li {
  width: 30%;
}
.BREADCRUMB {
  margin: 0 auto;
}
.LOGO {
  position: absolute;
}
</style>
