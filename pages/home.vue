<template>
  <q-page class="gradient-bg-primary q-pa-md" style="overflow:hidden">
    <div class="relative-position">
      <div
        class=" round-borders  shadow-14 bg-bg1 relative-position"
        style="min-height:600px; padding-bottom: 120px; overflow:hidden"
      >
        <div
          class="big_logo animate-scale"
          style="background-size: 200%;"
        ></div>
        <div
          class="row q-px-xl"
          style="margin-bottom:-40px; padding-top:40px; text-shadow: 2px 2px rgba(0,0,0,0.5);"
        >
          <div
            class="col-xs-12 col-lg-6 q-display-3 index-title"
            style="transition: font-size 0.5s"
          >
            {{ $t("index.welcome_to_esodac_member_client") }}
          </div>
        </div>
        <div class="row">
          <div
            class="col-xl-6 col-md-12 col-sm-12 col-xs-12  index_border_right_col q-px-xl"
            style="min-height:300px"
          >
            <div class="column justify-between full-height">
              <div
                class="q-title text-text2 regular index-description"
                style="padding-top:50px; transition: font-size 0.5s"
              >
                <p>{{ $t("index.description_p1") }}</p>
                <p>{{ $t("index.description_p2") }}</p>
              </div>
              <div class="q-mb-lg">
                <q-btn
                  v-if="!getAccountName"
                  class="float-left q-px-xl"
                  size="lg"
                  color="primary"
                  :label="$t('index.signin')"
                  @click="login"
                />
                <q-btn
                  v-else
                  class="float-left q-px-xl"
                  size="lg"
                  color="primary"
                  :label="$t('index.signout')"
                  @click="logout"
                />
              </div>
            </div>
          </div>
          <div class="col-xl-6 col-md-12 col-sm-12 col-xs-12 q-px-xl">
            <div class=" full-height">
              <div class="q-headline q-mb-lg">
                {{ $t("index.key_features") }}
              </div>

              <div class="row text-text1 gutter-sm">
                <q-item class="col-xs-12 col-md-6">
                  <q-item-side left
                    ><q-icon
                      :name="$configFile.icon.member"
                      size="48px"
                      class="q-mr-sm text-text2"
                  /></q-item-side>
                  <q-item-main
                    ><span class="q-title">{{
                      $t("index.reg_as_member")
                    }}</span></q-item-main
                  >
                </q-item>
                <q-item class=" col-xs-12 col-md-6">
                  <q-item-side left
                    ><q-icon
                      :name="$configFile.icon.work_prop"
                      size="48px"
                      class="q-mr-sm text-text2"
                  /></q-item-side>
                  <q-item-main
                    ><span class="q-title">{{
                      $t("index.submit_wp")
                    }}</span></q-item-main
                  >
                </q-item>
                <q-item class=" col-xs-12 col-md-6">
                  <q-item-side left
                    ><q-icon
                      :name="$configFile.icon.constitution"
                      size="48px"
                      class="q-mr-sm text-text2"
                  /></q-item-side>
                  <q-item-main
                    ><span class="q-title">{{
                      $t("index.read_constitution")
                    }}</span></q-item-main
                  >
                </q-item>

                <q-item class=" col-xs-12 col-md-6">
                  <q-item-side left
                    ><q-icon
                      name="account_balance_wallet"
                      size="48px"
                      class="q-mr-sm text-text2"
                  /></q-item-side>
                  <q-item-main
                    ><span class="q-title">{{
                      $t("index.wallet")
                    }}</span></q-item-main
                  >
                </q-item>
                <q-item class=" col-xs-12 col-md-6">
                  <q-item-side left
                    ><q-icon
                      :name="$configFile.icon.cand_reg"
                      size="48px"
                      class="q-mr-sm text-text2"
                  /></q-item-side>
                  <q-item-main
                    ><span class="q-title">{{
                      $t("index.reg_as_cust_cand")
                    }}</span></q-item-main
                  >
                </q-item>
                <q-item class=" col-xs-12 col-md-6">
                  <q-item-side left
                    ><q-icon
                      :name="$configFile.icon.vote"
                      size="48px"
                      class="q-mr-sm text-text2"
                  /></q-item-side>
                  <q-item-main
                    ><span class="q-title">{{
                      $t("index.vote_cust")
                    }}</span></q-item-main
                  >
                </q-item>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div
        class="row gutter-md relative-position justify-center q-px-md row_boxes_index_page"
        style="min-height:240px;"
      >
        <div
          class="col-xl-4 col-md-12 col-sm-12 col-xs-12"
          style="min-width:200px"
        >
          <div
            class="column justify-between bg-primary shadow-14 round-borders full-height q-pa-md animate-pop"
          >
            <div>
              <div class="q-title q-mb-lg">{{ $t("index.join_discord") }}</div>
              <div class="q-body-1 text-text2 relative-position">
                <q-icon
                  name="mdi-telegram"
                  size="48px"
                  class="absolute-top-left"
                />
                <div
                  style="display:inline-block;margin-left:55px;margin-top:-3px"
                >
                  {{ $t("index.discord_description") }}
                </div>
              </div>
            </div>
            <div class="q-mt-sm">
              <q-btn
                class="float-right"
                color="bg2"
                :label="$t('index.open_discord')"
                @click.native="openURL($configFile.get('external').telegram)"
              />
            </div>
          </div>
        </div>
        <div
          class="col-xl-4 col-md-12 col-sm-12 col-xs-12"
          style="min-width:200px"
        >
          <div
            class="column justify-between bg-primary shadow-14 round-borders full-height q-pa-md animate-pop"
          >
            <div>
              <div class="q-title q-mb-lg">{{ $t("index.visit_eosdac") }}</div>
              <div class="q-body-1 text-text2 relative-position">
                <q-icon
                  name="mdi-file-document-box-multiple-outline"
                  size="48px"
                  class="absolute-top-left"
                />
                <div
                  style="display:inline-block;margin-left:55px;margin-top:-3px"
                >
                  {{ $t("index.website_description") }}
                </div>
              </div>
            </div>
            <div class="q-mt-sm">
              <q-btn
                class="float-right"
                color="bg2"
                :label="$t('index.eosdac')"
                @click.native="openURL($configFile.get('external').whitepaper)"
              />
            </div>
          </div>
        </div>
        <div
          class="col-xl-4 col-md-12 col-sm-12 col-xs-12"
          style="min-width:200px"
        >
          <div
            class="column justify-between bg-primary shadow-14 round-borders full-height q-pa-md animate-pop"
          >
            <div>
              <div class="q-title q-mb-lg">
                Homepage
              </div>
              <div class="q-body-1 text-text2 relative-position">
                <q-icon
                  name="mdi-home-variant-outline"
                  size="48px"
                  class="absolute-top-left"
                />
                <div
                  style="display:block;margin-left:55px;margin-top:-3px; width: calc(100% - 55px);"
                >
                  Learn more about the Vigor decentralized stable coin project
                  by visiting our homepage.
                </div>
              </div>
            </div>

            <div
              class="q-mt-sm row justify-end items-center"
              style="min-height:50px"
            >
              <q-btn
                class=""
                color="bg2"
                label="Visit"
                @click.native="openURL($configFile.get('external').homepage)"
              />
            </div>
          </div>
        </div>
        <div
          class="col-xl-4 col-md-12 col-sm-12 col-xs-12"
          style="min-width:200px"
        >
          <div
            class="column justify-between bg-primary shadow-14 round-borders full-height q-pa-md animate-pop"
          >
            <div>
              <div class="q-title q-mb-lg">
                Github
              </div>
              <div class="q-body-1 text-text2 relative-position">
                <q-icon
                  name="mdi-github-box"
                  size="48px"
                  class="absolute-top-left"
                />
                <div
                  style="display:block;margin-left:55px;margin-top:-3px; width: calc(100% - 55px);"
                >
                  Contribute to the Vigor project
                </div>
              </div>
            </div>

            <div
              class="q-mt-sm row justify-end items-center"
              style="min-height:50px"
            >
              <q-btn
                class=""
                color="bg2"
                label="Visit"
                @click.native="openURL($configFile.get('external').github)"
              />
            </div>
          </div>
        </div>
      </div>
    </div>
  </q-page>
</template>

<script>
import { openURL } from "quasar";
import { mapGetters } from "vuex";
export default {
  components: {},
  data() {
    return {
      email_address: "",
      language: "",
      onsubscribemsg: "",
      loading: false
    };
  },

  computed: {
    ...mapGetters({
      getAccountName: "user/getAccountName",
      getIsDark: "ui/getIsDark"
    })
  },

  methods: {
    openURL,
    login() {
      this.$store.dispatch("global/login");
    },
    logout() {
      this.$store.dispatch("global/logout");
    },

    async subscribeNewsletter() {
      this.onsubscribemsg = "";
      let data = { email: this.email_address, language: this.language };

      if (!this.$helper.isEmail(this.email_address) || this.language == "") {
        this.onsubscribemsg = this.$t("index.valid_input_required");
        return false;
      }

      let url =
        this.$helper.noBackSlash(this.$configFile.get("memberclientapi")) +
        "/subscribe";

      this.loading = true;
      try {
        let result = await this.$axios.post(url, data);
        this.onsubscribemsg = this.$t("index." + result.data.message);
        // console.log(result);
      } catch (e) {
        this.onsubscribemsg = this.$t("index.error_occured");
        console.log(e);
      }
      this.clearForm();
    },

    clearForm() {
      this.loading = false;
      this.email_address = "";
      this.language = "";
    }
  }
};
</script>

<style lang="stylus">
@import '~variables'



.index_border_right_col{
  border-right:1px solid grey;
}
.row_boxes_index_page{
  top:-100px;
  transition: all .2s ease-in-out;
}
.partnerbox{
  top:0px;
  position:relative;
}


@media screen and (max-width: 1200px) {
  .partnerbox{
    top:40px!important;;
  }
  .row_boxes_index_page{
    top:20px !important;
  }
  .index_border_right_col{
    border-right: none !important;
  }

}
</style>
