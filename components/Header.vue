<template>
  <div>
    <!-- TOPBAR -->
    <scroll-fixed-header :fixed.sync="fixed" :threshold="56">
      <div class="waxon_tm_topbar">
        <div class="container">
          <div class="topbar_inner">
            <div class="logo">
              <router-link to="/">
                <img src="../assets/img/logo/dark.png" alt="partners brand" />
              </router-link>
            </div>
            <div class="menu">
              <div class="links">
                <ul class="anchor_nav">
                  <scrollactive
                    bezier-easing-value=".5,0,.35,1"
                    :offset="69"
                    :duration="100"
                    :alwaysTrack="true"
                  >
                    <li class="current">
                      <a href="#accueil" class="scrollactive-item">
                        <span class="first">Accueil</span>
                        <span class="second">Accueil</span>
                      </a>
                    </li>
                    <li>
                      <a href="#biographie" class="scrollactive-item">
                        <span class="first">Biographie</span>
                        <span class="second">Biographie</span>
                      </a>
                    </li>
                    <li>
                      <a href="#photos" class="scrollactive-item">
                        <span class="first">Photos</span>
                        <span class="second">Photos</span>
                      </a>
                    </li>
                    <li>
                      <a href="#avis" class="scrollactive-item">
                        <span class="first">Avis</span>
                        <span class="second">Avis</span>
                      </a>
                    </li>
                    <li>
                      <a href="#news" class="scrollactive-item">
                        <span class="first">News</span>
                        <span class="second">News</span>
                      </a>
                    </li>
                    <li>
                      <a href="#contact" class="scrollactive-item">
                        <span class="first">Contact</span>
                        <span class="second">Contact</span>
                      </a>
                    </li>
                  </scrollactive>
                </ul>
              </div>
            </div>
          </div>
        </div>
      </div>
    </scroll-fixed-header>
    <!-- /TOPBAR -->

    <!-- MOBILE MENU -->
    <div class="waxon_tm_mobile_menu">
      <div class="topbar_inner">
        <div class="container bigger">
          <div class="topbar_in">
            <div class="logo">
              <router-link to="/">
                <img src="../assets/img/logo/dark.png" alt="partners brand" />
              </router-link>
            </div>
            <div class="my_trigger">
              <div
                class="hamburger hamburger--collapse-r"
                :class="{ 'is-active': active }"
              >
                <div
                  class="hamburger-box"
                  @click="active = !active"
                  :aria-pressed="active ? 'true' : 'false'"
                >
                  <div class="hamburger-inner"></div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div
        class="dropdown"
        :class="{ active: active }"
        :style="{ backgroundImage: 'url(' + pattern + ')' }"
      >
        <div class="container">
          <span
            class="close_menu"
            @click="active = !active"
            :aria-pressed="active ? 'true' : 'false'"
          >
            <img src="../assets/img/close.svg" alt="close menu" />
          </span>
          <div class="dropdown_inner">
            <ul class="anchor_nav">
              <scrollactive
                bezier-easing-value=".5,0,.35,1"
                :offset="76"
                :duration="100"
                :alwaysTrack="true"
              >
                <li>
                  <a
                    href="#accueil"
                    class="scrollactive-item"
                    @click="active = !active"
                    >Accueil</a
                  >
                </li>
                <li>
                  <a
                    href="#biographie"
                    class="scrollactive-item"
                    @click="active = !active"
                    >Biographie</a
                  >
                </li>
                <li>
                  <a
                    href="#portfolio"
                    class="scrollactive-item"
                    @click="active = !active"
                    >Portfolio</a
                  >
                </li>
                <li>
                  <a
                    href="#news"
                    class="scrollactive-item"
                    @click="active = !active"
                    >News</a
                  >
                </li>
                <li>
                  <a
                    href="#contact"
                    class="scrollactive-item"
                    @click="active = !active"
                    >Contact</a
                  >
                </li>
              </scrollactive>
            </ul>
            <div class="mobile-social">
              <Social />
            </div>
            <!-- End social share -->
          </div>
        </div>
      </div>
    </div>
    <!-- /MOBILE MENU -->
  </div>
</template>

<script>
import Social from "../components/Social.vue";
export default {
  components: {
    Social,
  },
  data() {
    return {
      active: false,
      fixed: false,
      pattern: require("../assets/img/patterns/1.png"),
    };
  },
};
</script>

<style lang="scss" scoped></style>
