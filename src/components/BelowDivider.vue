<template>
  <div class="main">
    <div class="content">
      <div class="cardsGridBelowDivider">
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
    <div class="loadMore">
      <button class="loadMoreButton">Load more</button>
    </div>
  </div>
</template>
<script>
export default {
  data: () => ({
    loading: false,
    selection: 1,
    cards: [
      {
        src: require("../assets/card5.png"),
        title: "Life tastes better with coffee",
        desc: `Lorem ipsum dolor sit amet, consectetur adipisicing elit,
                    sed do eiusmod tempor incididunt ut labore et dolore magna
                    aliqua. Ut enim ad minim veniam, quis nostrud exercitation
                    ullamco laboris`,
        cat: "LIFESTYLE",
      },
      {
        src: require("../assets/card6.png"),
        title: "More than just a music festival",
        desc: `Lorem ipsum dolor sit amet, consectetur adipisicing elit,
                    sed do eiusmod tempor incididunt ut labore et dolore magna
                    aliqua. Ut enim ad minim veniam, quis nostrud exercitation
                    ullamco laboris`,
        cat: "LIFESTYLE",
      },
    ],
  }),
};
</script>
<style>
.cardsGridBelowDivider {
  padding-top: 52px;
  padding-left: 82px;
}
.loadMore {
  padding-left: 45.14%;
  padding-right: 48.872%;
}
.loadMoreButton {
  font-family: PlayfairDisplay-Regular, AdobeInvisFont, MyriadPro-Regular;
  font-size: 20px !important;
  color: rgba(98, 98, 98, 255) !important;
  padding: 17px 34px;
  width: 164px;
  border: 1px solid #626262;
}
@media only screen and (min-width: 1200px) {
  .cardGridColumn {
    padding: 0px !important;
  }
  .cardImage {
    width: 420px;
  }
}
@media only screen and (min-width: 768px) and (max-width: 1024px) {
  .cardsGridBelowDivider {
    padding: 40px;
    padding-bottom: 0px;
  }
}
@media only screen and (max-width: 960px) {
  .v-card {
    max-width: 100% !important;
  }
  .cardImage {
    width: 900px !important;
    height: 500px !important;
  }
}
@media only screen and (min-width: 768px) and (max-width: 1024px) {
  .cardsGridBelowDivider {
    padding: 40px;
    padding-bottom: 0px;
  }
}
@media only screen and (min-width: 425px) and (max-width: 768px) {
  .cardsGridBelowDivider {
    padding: 40px;
    padding-bottom: 0px;
  }
  .loadMore {
    padding-left: 38.82%;
    padding-right: 0px;
  }
}
@media only screen and (max-width: 425px) {
  .cardsGridBelowDivider {
    padding: 0px;
  }
  .loadMore {
    padding-left: 122px;
    padding-right: 122px;
  }
  .loadMoreButton {
    padding: 5px 12px;
  }
}
@media only screen and  (max-width: 325px) {
  .loadMore {
    padding-left: 0px;
  }
}
</style>
