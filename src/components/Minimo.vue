<template>
  <div>
    <div class="navBarButton">
      <header class="w3-container headBar">
        <span class="w3-opennav w3-xlarge">
          <div
            class="menuContainer"
            v-click-outside="onClickOutside"
            @click="handleMenuClick()"
          >
            <div class="bar1"></div>
            <div class="bar2"></div>
            <div class="bar3"></div>
          </div>
        </span>
      </header>
      <nav
        ref="sidenav"
        class="w3-sidenav w3-white w3-card-2 sideNav"
        style="display:none"
      >
        <a>
          <img
            width=""
            height=""
            aspect-ratio="5.173"
            class="minimologo"
            src="../assets/minimologo.png"
            alt="LOGO"
          />
        </a>
        <a class="lifestyle">LIFESTYLE</a>
        <a class="photodiary">PHOTODIARY</a>
        <a class="music">MUSIC</a>
        <a class="travel">TRAVEL</a>
      </nav>
    </div>
    <div class="main">
      <nav v-show="true">
        <div class="d-flex topbar">
          <img
            width=""
            height=""
            aspect-ratio="5.173"
            class="minimologo"
            src="../assets/minimologo.png"
            alt="LOGO"
          />
          <div class="d-flex nav-right">
            <div class="lifestyle">LIFESTYLE</div>
            <div class="photodiary">PHOTODIARY</div>
            <div class="music">MUSIC</div>
            <div class="travel">TRAVEL</div>
          </div>
        </div>
      </nav>
      <div class="content">
        <div class="firstpost">
          <img
            width="99.8125%"
            aspect-ratio="1.574"
            height=""
            src="../assets/firstpost.png"
            alt=""
          />
        </div>
        <div class="contentBelowFirstPost">PHOTODIARY</div>
        <div class="contentFirstPostTitle">The perfect weekend getaway</div>
        <div class="contentFirstPostDescription">
          <p>
            Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do
            eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim
            ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut
            aliquip ex ea commodo consequat. Duis aute irure dolor in
            reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla
            pariatur. Excepteur sint occaecat cupidatat non proident, sunt in
            culpa qui officia deserunt mollit anim id est laborum. Sed ut
            perspiciatis unde omnis iste natus error sit voluptatem accusantium
            doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo
            inventore veritatis et quasi architecto beatae vitae dicta sunt
            explicabo. Nemo enim ipsam voluptatem quia voluptas sit aspernatur
            aut odit aut fugit, sed quia consequuntur magni dolores eos qui
            ratione voluptatem sequi nesciunt. Neque porro quisquam est, qui
            dolorem ipsum quia dolor sit amet, consectetur, adipisci velit, sed
            quia non numquam eius modi tempora incidunt ut labore et dolore
            magnam aliquam quaerat voluptatem.
          </p>
        </div>
        <div class="contentFirstPostComment">LEAVE A COMMENT</div>

        <div class="cardsGrid">
          <v-row>
            <v-col
              lg="6"
              md="6"
              sm="12"
              xs="12"
              class="cardGridColumn d-flex justify-center"
              v-for="(item, index) in cards"
              :key="index"
            >
              <v-card :loading="loading" max-width="474">
                <template slot="progress">
                  <v-progress-linear
                    color="deep-purple"
                    height="10"
                    indeterminate
                  ></v-progress-linear>
                </template>

                <v-img
                  v-show="true"
                  class="cardImage"
                  ref="cardImage"
                  fluid
                  height="280"
                  :src="item.src"
                ></v-img>

                <v-card-title>
                  <div class="card-heading">{{ item.cat }}</div>
                </v-card-title>

                <v-card-text class="card-text">
                  <div class="card-title ">
                    {{ item.title }}
                  </div>

                  <div class="card-description">
                    {{ item.desc }}
                  </div>
                </v-card-text>
              </v-card>
            </v-col>
          </v-row>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import vClickOutside from "v-click-outside";
export default {
  data() {
    return {
      loading: false,
      directives: {
        clickOutside: vClickOutside.directive,
      },
      cards: [
        {
          src: require("../assets/card1.png"),
          title: "Life tastes better with coffee",
          desc: `Lorem ipsum dolor sit amet, consectetur adipisicing elit,
                    sed do eiusmod tempor incididunt ut labore et dolore magna
                    aliqua. Ut enim ad minim veniam, quis nostrud exercitation
                    ullamco laboris`,
          cat: "LIFESTYLE",
        },
        {
          src: require("../assets/card2.png"),
          title: "More than just a music festival",
          desc: `Lorem ipsum dolor sit amet, consectetur adipisicing elit,
                    sed do eiusmod tempor incididunt ut labore et dolore magna
                    aliqua. Ut enim ad minim veniam, quis nostrud exercitation
                    ullamco laboris`,
          cat: "LIFESTYLE",
        },
        {
          src: require("../assets/card3.png"),
          title: "American dream",
          desc: `Lorem ipsum dolor sit amet, consectetur adipisicing elit,
                    sed do eiusmod tempor incididunt ut labore et dolore magna
                    aliqua. Ut enim ad minim veniam, quis nostrud exercitation
                    ullamco laboris`,
          cat: "PHOTODIARY",
        },
        {
          src: require("../assets/card4.png"),
          title: "A day exploring the Alps",
          desc: `Lorem ipsum dolor sit amet, consectetur adipisicing elit,
                    sed do eiusmod tempor incididunt ut labore et dolore magna
                    aliqua. Ut enim ad minim veniam, quis nostrud exercitation
                    ullamco laboris`,
          cat: "PHOTODIARY",
        },
      ],
    };
  },
  mounted() {},
  methods: {
    onClickOutside() {
      if (this.$refs.sidenav.style.display === "block") this.closeMenu();
      else return;
    },
    handleMenuClick() {
      if (this.$refs.sidenav.style.display === "none") this.openMenu();
      else {
        this.closeMenu();
      }
    },
    openMenu() {
      document
        .getElementsByClassName("menuContainer")[0]
        .classList.toggle("change");
      this.$refs.sidenav.style.display = "block";
    },
    closeMenu() {
      document
        .getElementsByClassName("menuContainer")[0]
        .classList.toggle("change");
      this.$refs.sidenav.style.display = "none";
    },

    reserve() {
      this.loading = true;

      setTimeout(() => (this.loading = false), 2000);
    },
  },
};
</script>

<style>
@import "../assets/stylesheets/stylesheet.css";
.headBar {
  width: 100%;
  z-index: 9999;
}
.sideNav {
  margin-top: 40px !important;
}

.main {
  max-width: 1200px;
  margin-left: auto;
  margin-right: auto;
  padding: 68px;
  padding-bottom: 0px;
}
nav {
  height: 26px;
}
.minimo {
  font-family: Inconsolata-Regular, AdobeInvisFont, MyriadPro-Regular;
  font-size: 30pt;
  color: rgba(0, 0, 0, 255);
  text-align: center;
  margin-right: 36.84%;
}

.menuContainer {
  display: inline-block;
  cursor: pointer;
  margin-right: 23px;
}

.bar1,
.bar2,
.bar3 {
  width: 35px;
  height: 5px;
  background-color: #333;
  margin: 6px 0;
  transition: 0.4s;
}

.change .bar1 {
  -webkit-transform: rotate(-45deg) translate(-9px, 6px);
  transform: rotate(-45deg) translate(-9px, 6px);
}

.change .bar2 {
  opacity: 0;
}

.change .bar3 {
  -webkit-transform: rotate(45deg) translate(-8px, -8px);
  transform: rotate(45deg) translate(-8px, -8px);
}

.topbar {
  display: flex;
  width: auto;
}
.topbar .minimologo {
  margin-right: 35.84%;
}

.nav-right {
  display: flex;
  width: auto;
}

.topbar div,
.lifestyle,
.photodiary,
.music,
.travel {
  font-family: PlayfairDisplay-Regular, AdobeInvisFont, MyriadPro-Regular;
  font-size: 14px;
  color: rgba(98, 98, 98, 255);
  text-align: center;
}
.topbar .lifestyle {
  margin-right: 40.5%;
}
.topbar .photodiary {
  margin-right: 39.5%;
}
.topbar .music {
  margin-right: 36.43%;
}
.firstpost {
  margin-bottom: 99px;
}
.contentBelowFirstPost {
  font-family: Ubuntu-Light, AdobeInvisFont, MyriadPro-Regular;
  font-size: 16px;
  color: rgba(180, 173, 158, 255);
  text-align: left;
  padding-left: 7.7%;
}
.contentFirstPostTitle {
  font-family: PlayfairDisplay-Regular, AdobeInvisFont, MyriadPro-Regular;
  font-size: 30pt;
  color: rgba(98, 98, 98, 255);
  text-align: left;
  padding-left: 7.69%;
  margin-top: 2.63%;
  margin-bottom: 3.2%;
}
.contentFirstPostDescription {
  padding-left: 7.528%;
  padding-right: 8.359%;
}
.contentFirstPostDescription p {
  font-family: PlayfairDisplay-Regular, AdobeInvisFont, MyriadPro-Regular;
  font-size: 16px;
  color: rgba(98, 98, 98, 255);
  text-align: left;
  margin-bottom: 52px;
}
.contentFirstPostComment {
  font-family: Ubuntu-Light, AdobeInvisFont, MyriadPro-Regular;
  font-size: 16px;
  color: rgba(180, 173, 158, 255);
  text-align: left;
  padding-left: 7.7%;
}
.cardsGrid {
  padding-left: 82px;
  padding-top: 134px;
}
.cardGridColumn {
  margin-bottom: 130px;
}
.card-heading {
  font-family: Ubuntu-Light, AdobeInvisFont, MyriadPro-Regular;
  font-size: 14pt;
  color: rgba(180, 173, 158, 255);
  text-align: left;
  margin-top: 12px;
}
.card-title {
  font-family: PlayfairDisplay-Regular, AdobeInvisFont, MyriadPro-Regular;
  font-size: 33px;
  line-height: 33px;
  color: rgba(98, 98, 98, 255);
  text-align: left;
  padding: 20px 0px;
}
.card-description {
  font-family: PlayfairDisplay-Regular, AdobeInvisFont, MyriadPro-Regular;
  font-size: 17px;
  color: rgba(98, 98, 98, 255);
  text-align: left;
}
.v-sheet.v-card:not(.v-sheet--outlined) {
  box-shadow: none !important;
}
.v-card__subtitle,
.v-card__text,
.v-card__title {
  padding: 0px 0px !important;
}

.card-title {
  margin-bottom: 18px;
}
.card-text {
  padding: 20px 0px;
}

@media only screen and (min-width: 1024px) and (max-width: 1200px) {
  
  nav {
    display: none;
  }
  .main {
    padding: 8px;
    padding-bottom: 0px;
  }
  .cardsGrid {
    padding: 40px;
    padding-bottom: 0px;
  }
}
@media only screen and (min-width: 768px) and (max-width: 1024px) {
  nav {
    display: none;
  }
  .main {
    padding: 8px;
    padding-bottom: 0px;
  }
  .contentFirstPostTitle {
    font-size: 30pt;
  }
  .cardsGrid {
    padding: 40px;
    padding-bottom: 0px;
  }
}
@media only screen and (min-width: 425px) and (max-width: 768px) {
  nav {
    display: none;
  }
  .main {
    padding: 8px;
    padding-bottom: 0px;
  }
  .contentFirstPostTitle {
    font-size: 24pt;
  }
  .cardsGrid {
    padding: 40px;
    padding-bottom: 0px;
  }
}
@media only screen and (min-width: 179px) and (max-width: 425px) { 
  nav {
    display: none;
  }
  .main {
    padding: 8px;
    padding-bottom: 0px;
  }
  .contentFirstPostTitle {
    font-size: 24pt;
  }
  .cardsGrid {
    padding: 0px;
  }
}
@media only screen and (min-width: 1200px) {
  .navBarButton {
    display: none;
  }
}
</style>
