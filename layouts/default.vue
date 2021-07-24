<template>
  <v-app dark>
    <v-app-bar
      fixed
      flat
      color="white"
      app
    >
      <v-container class="d-flex flex-nowrap align-center">
        <v-toolbar-title v-text="title" />
        <v-spacer />
        <v-menu offset-y>
          <template #activator="{ on, attrs }">
            <v-btn
              v-bind="attrs"
              v-on="on"
            >
              <v-icon>mdi-account-circle-outline</v-icon>
            </v-btn>
          </template>
          <v-list min-width="120" dense elevation="9">
            <v-list-item>
              <v-list-item-title>
                ثبت نام
              </v-list-item-title>
            </v-list-item>
            <v-divider />
            <v-list-item>
              <v-list-item-title>
                ورود
              </v-list-item-title>
            </v-list-item>
          </v-list>
        </v-menu>

        <v-divider class="mx-2" vertical inset />
        <v-btn depressed>
          <v-icon left>
            mdi-wallet-outline
          </v-icon>
          کیف پول
        </v-btn>
      </v-container>
    </v-app-bar>

    <v-main>
      <v-toolbar flat color="error" short>
        <v-container>
          <v-menu
            open-on-hover
            offset-y
            :close-on-content-click="false"
            rounded="0"
            min-width="100%"
            transition="slide-y-transition"
          >
            <template #activator="{ on, attrs,value }">
              <v-btn
                v-bind="attrs"
                depressed
                color="transparent"
                dark

                v-on="on"
              >
                لاتاری ها
                <v-icon
                  v-anime="{
                    rotate: !value? '0deg' : '180deg',
                    translateY: !value? '0px' : '2px',
                  }"
                  right
                >
                  mdi-chevron-down
                </v-icon>
              </v-btn>
            </template>
            <v-card rounded="0" elevation="9">
              <v-container>
                <v-row>
                  <v-col cols="12">
                    items
                  </v-col>
                  <v-col cols="12" align-self="center" class="justify-center d-flex">
                    <v-btn outlined large color="primary">
                      مشاهده همه
                    </v-btn>
                  </v-col>
                </v-row>
              </v-container>
            </v-card>
          </v-menu>

          <v-divider class="mx-2" vertical inset />
          <v-btn depressed color="transparent" dark>
            پشتیبانی
          </v-btn>
        </v-container>
      </v-toolbar>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
export default {
  data () {
    return {
      items: [
        {
          icon: 'mdi-apps',
          title: 'Welcome',
          to: '/'
        }
      ],
      title: 'لاتاریمون'
    }
  }
}
</script>
