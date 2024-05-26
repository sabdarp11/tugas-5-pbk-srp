<template>
  <q-layout view="lHh Lpr lFf" class="bg-pink-5 text-white">
    <!-- Header Section -->
    <q-header elevated class="bg-pink-3">
      <q-toolbar>
        <q-btn dense flat round icon="menu" @click="toggleLeftDrawer" />
        <q-toolbar-title class="text-center">
          <q-avatar>
            <img src="https://cdn.quasar.dev/logo-v2/svg/logo-mono-white.svg" />
          </q-avatar>
          SABDA STORE
        </q-toolbar-title>
      </q-toolbar>
    </q-header>

    <!-- Left Drawer Section -->
    <q-drawer
      show-if-above
      v-model="leftDrawerOpen"
      side="left"
      class="bg-pink-5"
      bordered
    >
      <q-list class="bg-pink-3 border-radius" dark>
        <q-item-label header class="header-label text-center"
          ><b>SABDA STORE</b></q-item-label
        >
        <q-item
          clickable
          target="_blank"
          rel="noopener"
          href="https://example.com/home"
        >
          <q-item-section avatar>
            <q-icon name="home" />
          </q-item-section>
          <q-item-section>
            <q-item-label>Beranda</q-item-label>
            <q-item-label caption></q-item-label>
          </q-item-section>
        </q-item>

        <q-item
          clickable
          target="_blank"
          rel="noopener"
          href="https://example.com/check-transaction"
        >
          <q-item-section avatar>
            <q-icon name="receipt_long" />
          </q-item-section>
          <q-item-section>
            <q-item-label>Cek Transaksi</q-item-label>
            <q-item-label caption></q-item-label>
          </q-item-section>
        </q-item>

        <q-item
          clickable
          target="_blank"
          rel="noopener"
          href="https://example.com/services"
        >
          <q-item-section avatar>
            <q-icon name="list" />
          </q-item-section>
          <q-item-section>
            <q-item-label>Daftar Layanan</q-item-label>
            <q-item-label caption></q-item-label>
          </q-item-section>
        </q-item>

        <q-item
          clickable
          target="_blank"
          rel="noopener"
          href="https://example.com/faq"
        >
          <q-item-section avatar>
            <q-icon name="help" />
          </q-item-section>
          <q-item-section>
            <q-item-label>FAQ</q-item-label>
            <q-item-label caption></q-item-label>
          </q-item-section>
        </q-item>

        <q-item
          clickable
          target="_blank"
          rel="noopener"
          href="https://example.com/api"
        >
          <q-item-section avatar>
            <q-icon name="code" />
          </q-item-section>
          <q-item-section>
            <q-item-label>API</q-item-label>
            <q-item-label caption></q-item-label>
          </q-item-section>
        </q-item>

        <q-item
          clickable
          target="_blank"
          rel="noopener"
          href="https://example.com/login"
        >
          <q-item-section avatar>
            <q-icon name="login" />
          </q-item-section>
          <q-item-section>
            <q-item-label>Masuk</q-item-label>
            <q-item-label caption></q-item-label>
          </q-item-section>
        </q-item>

        <q-item
          clickable
          target="_blank"
          rel="noopener"
          href="https://example.com/register"
        >
          <q-item-section avatar>
            <q-icon name="person_add" />
          </q-item-section>
          <q-item-section>
            <q-item-label>Daftar</q-item-label>
            <q-item-label caption></q-item-label>
          </q-item-section>
        </q-item>

        <q-item
          clickable
          target="_blank"
          rel="noopener"
          href="https://example.com/check-transaction"
        >
          <q-item-section avatar>
            <q-icon name="settings" />
          </q-item-section>
          <q-item-section>
            <q-item-label>Pengaturan</q-item-label>
            <q-item-label caption></q-item-label>
          </q-item-section>
        </q-item>
      </q-list>
    </q-drawer>

    <!-- Main Page Container -->
    <q-page-container>
      <div class="q-pa-md">
        <q-carousel swipeable animated v-model="slide" thumbnails infinite>
          <q-carousel-slide :name="1" img-src="/assets/ml.png " />
          <q-carousel-slide :name="2" img-src="/assets/ml1.jpg" />
          <q-carousel-slide :name="3" img-src="/assets/ml2.jpg" />
          <q-carousel-slide :name="4" img-src="/assets/ml3.jpg" />
        </q-carousel>

        <div class="row justify-center q-gutter-sm">
          <q-intersection v-for="item in items" :key="item.id" transition="scale" class="example-item">
            <q-card flat bordered class="q-ma-sm card-item">
              <div class="card-content">
                <img :src="item.imageUrl" alt="Image description" class="card-image" />
                <q-card-section class="text-center">
                  <div class="text-h6 card-title">{{ item.title }}</div>
                </q-card-section>
              </div>
            </q-card>
          </q-intersection>
        </div>
        <router-view />
      </div>
    </q-page-container>

    <!-- Footer Section -->
    <q-footer elevated class="bg-pink-3 text-white">
      <q-toolbar class="justify-center" style="height: 10px">
        <q-toolbar-title class="text-center">
          <q-avatar> </q-avatar>
          <div class="footer-text"><b>Copyright Sabda Rp 2024.</b></div>
        </q-toolbar-title>
      </q-toolbar>
    </q-footer>
  </q-layout>

  <q-footer elevated>
    <q-toolbar>
      <q-toolbar-title>Footer</q-toolbar-title>
    </q-toolbar>
  </q-footer>
</template>

<script>
import { ref, onMounted, onUnmounted } from "vue";

export default {
  name: "MyLayout",

  data() {
    return {
      items: [  // Array moved to data() for reactivity
        { id: 1, imageUrl: "/assets/ml icon.jpg", title: "Mobile Legends" },
        { id: 2, imageUrl: "/assets/8ballpoll.jpg", title: "8 ball poll" },
        { id: 3, imageUrl: "/assets/coc.jpg", title: "Clash Of Clans" },
        { id: 4, imageUrl: "/assets/fcmobile.jpg", title: "FC Mobile" },
        { id: 5, imageUrl: "/assets/Freefire.jpg", title: "FreeFire" },
        { id: 6, imageUrl: "/assets/genshin.jpg", title: "Genshin Impact" },
        { id: 7, imageUrl: "/assets/pubg.jpg", title: "PUBG Mobile" },
        { id: 8, imageUrl: "/assets/subway.jpg", title: "Subway Surfest" },
        { id: 9, imageUrl: "/assets/valo.jpg", title: "Valorant" },
        { id: 10, imageUrl: "/assets/codm.jpg", title: "Call Of Duty" },
      ]
    };
  },

  setup() {
    const slide = ref(1);
    const leftDrawerOpen = ref(false);
    const rightDrawerOpen = ref(false);

    function toggleLeftDrawer() {
      leftDrawerOpen.value = !leftDrawerOpen.value;
    }

    function toggleRightDrawer() {
      rightDrawerOpen.value = !rightDrawerOpen.value;
    }

    const nextSlide = () => {
      slide.value = (slide.value % 4) + 1;
    };

    let slideInterval;

    onMounted(() => {
      slideInterval = setInterval(nextSlide, 2000); // Slide change interval set to 2 seconds
    });

    onUnmounted(() => {
      clearInterval(slideInterval);
    });

    return {
      slide,
      leftDrawerOpen,
      toggleLeftDrawer,
      rightDrawerOpen,
      toggleRightDrawer,
    };
  },
};

</script>

<style>
.app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.bg-pink-5 {
  background-color: #ff69b4; 
}

.bg-pink-3 {
  background-color: #ff85b4;
}

.example-item {
  height: 290px;
  width: 290px;
}

.footer-text {
  margin-top: -30px;
}

.border-radius {
  border-radius: 30px;
}

.header-label {
  position: relative;
  padding-bottom: 10px;
}

.header-label::after {
  content: "";
  position: absolute;
  left: 50%;
  bottom: 0;
  transform: translateX(-50%);
  width: 80%;
  height: 3px;
  background-color: rgb(0, 0, 0);
  border-radius: 2px;
}

.card-item {
  width: 200px;
}

.card-image {
  max-width: 100%;
}

.card-title {
  background-color: #ffccd3;
  color: black;
  padding: 10px;
  border-radius: 5px;
}

</style>