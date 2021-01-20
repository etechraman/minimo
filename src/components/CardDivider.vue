<template>
  <div class="cardsDivider">
    <div class="cardsDividerContent">
      <div class="signup">Sign up for our newsletter!</div>
      <div class="enterEmail">
        <v-container>
          <v-row
            ><v-col cols="12" class="enterEmailAddress">
              <v-text-field label="Enter a valid email address" clearable
                ><template slot="append">
                  <v-img src="../assets/sendIcon.png"></v-img>
                </template>
              </v-text-field> </v-col
          ></v-row>
        </v-container>
      </div>
    </div>
  </div>
</template>
<style>
.ddddd {
  font-family: PlayfairDisplay-Regular, AdobeInvisFont, MyriadPro-Regular;
  font-size: 15px;
  color: rgba(98, 98, 98, 255);
  text-align: left;
}
.cardsDivider {
  width: 100%;
  background-color: #cccccc;
}
.cardsDividerContent {
  max-width: 1200px;
  padding: 4.08% 22.7%;
  margin: 0px auto;
  display: flex;
  flex-direction: column;
  width: max-content;
}
.row {
  margin: 0px !important;
}
.signup {
  font-family: PlayfairDisplay-Regular, AdobeInvisFont, MyriadPro-Regular;
  font-size: 33px;
  color: rgba(51, 51, 51, 255);
  text-align: center;
}
.enterEmail {
  max-width: 425px;
  margin-top: 83px;
}
.enterEmailAddress {
  padding: 0px !important;
  font-family: PlayfairDisplay-Regular, AdobeInvisFont, MyriadPro-Regular;
  font-size: 14pt;
  color: rgba(98, 98, 98, 255);
  text-align: left;
  margin-right: 32.7%;
}
.sendIcon {
  padding: 0px !important;
  font-family: PlayfairDisplay-Regular, AdobeInvisFont, MyriadPro-Regular;
  font-size: 14pt;
  color: rgba(98, 98, 98, 255);
  text-align: right;
}
.line {
  padding-left: 0px !important;
}
@media only screen and (max-width: 1200px) {
  .cardsDividerContent {
    width: 100% !important;
    padding: 4.01% 22.35% !important;
    margin: 0px auto;
    align-items: center;
  }
  .enterEmail v-img {
    width: 50px;
  }
}
</style>
