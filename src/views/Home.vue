<template>
  <v-app id="inspire">
    <v-navigation-drawer v-model="drawer">
      <!--  -->
      <v-list-subheader>&nbsp;&nbsp;&nbsp;MENU</v-list-subheader>
      <v-list-item-subtitle>&nbsp;&nbsp;&nbsp;Escolha uma opção</v-list-item-subtitle>
      <v-card>
        <v-layout>
          <v-navigation-drawer floating permanent>
            <v-list density="compact" nav>
              <!-- <v-list-subheader>REPORTS</v-list-subheader> -->
              <!-- <v-tabs v-model="tab" direction="vertical" color="primary"> -->
              <v-list-item v-for="(item, i) in itemsM" :key="i" :value="item" :to="item.to" color="primary" rounded="sm">

                <template v-slot:prepend>
                  <v-icon :icon="item.icon"></v-icon>
                </template>

                <v-list-item-title v-text="item.text"></v-list-item-title>

              </v-list-item>
              <!-- {{ item }} -->
              <!-- </v-tabs> -->
            </v-list>

            <!-- <v-list v-model="tab" density="compact" nav>
              <v-list-item prepend-icon="mdi-view-dashboard" title="Home" value="home"></v-list-item>
              <v-list-item prepend-icon="mdi-account" title="Contactos" value="cnt"></v-list-item>
              <v-list-item prepend-icon="mdi-account-group" title="Grupos" value="grp"></v-list-item>
              <v-list-item prepend-icon="mdi-account-voice" title="Campanhas" value="cmp"></v-list-item>
              <v-list-item prepend-icon="mdi-account-clock" title="Agendamento" value="cnl"></v-list-item>
              <v-list-item prepend-icon="mdi-message-plus" title="Mensagem" value="msg"></v-list-item>
              <v-list-item prepend-icon="mdi-forum" title="About" value="about"></v-list-item>
              <v-list-item prepend-icon="mdi-phone-settings" title="Chamadas" value="cal"></v-list-item>
              <v-list-item prepend-icon="mdi-whatsapp" title="WhatsApp" value="wht"></v-list-item>
              <v-list-item prepend-icon="mdi-email-fast-outline" title="E-mail" value="eml"></v-list-item>
              <v-list-item prepend-icon="mdi-cog" title="Configurações" value="set"></v-list-item>
            </v-list> -->
          </v-navigation-drawer>
          <v-main style="height: 750px"></v-main>
        </v-layout>
      </v-card>
    </v-navigation-drawer>

    <v-app-bar color="primary">
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

      <v-toolbar-title><v-icon>mdi-phone-message</v-icon>&nbsp;uKanda</v-toolbar-title>


      <!-- <v-spacer></v-spacer> -->


      <v-text-field @update:focused="searchClosed = false" @keydown.enter="greet(searchValue)"
        @esc.enter="greet(searchValue)" @blur="searchClosed = true" v-model="searchValue" placeholder="Procurar"
        prepend-inner-icon="mdi-magnify" class="expanding-search mt-1"
        :style="{ color: 'white', fontSize: '10px', borderRadius: '20px', fontWeight: 500, paddingTop: '0px', transitionDuration: 'max-width 0.3s' }"
        :class="{ 'closed': searchClosed && !search && !searchValue }" filled single-line dense clearable>

      </v-text-field>
      <!-- 
      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn> -->


      <v-btn icon color="white">
        <v-icon>mdi-plus-thick</v-icon>
        <v-menu activator="parent">
          <v-list>
            <v-list-item v-for="(item, index) in itemsM" :key="index" :value="index">
              <v-list-item-title> <v-icon>{{ item.icon }}</v-icon>&nbsp;{{ item.title }}</v-list-item-title>
            </v-list-item>
          </v-list>
        </v-menu>
      </v-btn>


      <v-btn icon>
        <v-icon>mdi-dots-vertical</v-icon>

        <v-menu activator="parent">
          <v-list>
            <v-list-item v-for="(item, index) in itemss" :key="index" :value="index">
              <v-list-item-title> <v-icon>{{ item.icon }}</v-icon>&nbsp;{{ item.title }}</v-list-item-title>
            </v-list-item>
          </v-list>
        </v-menu>
      </v-btn>


    </v-app-bar>

    <v-main>

      <!-- <v-breadcrumbs :items="['Foo', 'Bar', 'Fizz']"></v-breadcrumbs> -->
      <!--  -->
   
  <v-sheet
    class="mx-auto"
    max-width="100%"
  >
    <v-slide-group
      show-arrows
    >
      <v-slide-group-item
        v-for="n in tabMenus"
        :key="n"
        v-slot="{ isSelected, toggle }"
      >
        <!-- <v-btn
          class="ma-2"
          rounded
          :color="isSelected ? 'primary' : undefined"
          @click="toggle"
        >
          Options {{ n }}
        </v-btn> -->
        <v-card width="350" height="200" class="overflow-hidden pa-l ma-2"
            color="#ccfg4a"
            theme="dark"
          >
            <v-card-title class="text-h5">              
              <v-icon>{{ n.icon }}</v-icon>&nbsp;{{ n.title }}
              <v-label>{{ n.text }}</v-label>
            </v-card-title>

            <v-card-subtitle style="">Listen to your favorite artists and albums whenever and wherever, online and offline.</v-card-subtitle>

            <v-card-actions>
              <v-btn variant="text">
                Expandir
                <v-icon
                color="orange-darken-4"
                end
              >
                mdi-open-in-new
              </v-icon>
              </v-btn>
            </v-card-actions>
          </v-card>
      </v-slide-group-item>
    </v-slide-group>
  </v-sheet>



 
      

 

        
        
        
  






  
 



   

      <!-- </v-container> -->

      <!-- 
  <v-container class="bg-surface-variant">
    <v-row
      class="mb-1"
      no-gutters
    >
      <v-col>
        <v-sheet class="pa-2 ma-2">
          .v-col-auto
        </v-sheet>
      </v-col>

      <v-col>
        <v-sheet class="pa-2 ma-2">
          .v-col-auto
        </v-sheet>
      </v-col>

      <v-col>
        <v-sheet class="pa-2 ma-2">
          .v-col-auto
        </v-sheet>
      </v-col>

      <v-col>
        <v-sheet class="pa-2 ma-2">
          .v-col-auto
        </v-sheet>
      </v-col>
    </v-row>

    <v-row no-gutters>
      <v-col cols="8">
        <v-sheet class="pa-2 ma-2">
          .v-col-8
        </v-sheet>
      </v-col>

      <v-col cols="4">
        <v-sheet class="pa-2 ma-2">
          .v-col-4
        </v-sheet>
      </v-col>
    </v-row>
  </v-container> -->

      <!-- <v-divider :thickness="1" inset></v-divider> -->




      <!-- <template> -->
      <!-- <v-row justify="center">
        <v-dialog v-model="dialog" fullscreen :scrim="false" transition="dialog-bottom-transition" style="">
          <template v-slot:activator="{ props }">
            <v-btn color="primary" tonal v-bind="props">
              Open Dialog
            </v-btn>
          </template>
          <v-card>
            <v-toolbar dark color="primary">
              <v-btn icon dark @click="dialog = false">
                <v-icon>mdi-close</v-icon>
              </v-btn>
              <v-toolbar-title>Settings</v-toolbar-title>
              <v-spacer></v-spacer>
              <v-toolbar-items>
                <v-btn variant="text" @click="dialog = false">
                  Save
                </v-btn>
              </v-toolbar-items>
            </v-toolbar>
            <v-list lines="two" subheader>
              <v-list-subheader>User Controls</v-list-subheader>
              <v-list-item title="Content filtering"
                subtitle="Set the content filtering level to restrict apps that can be downloaded"></v-list-item>
              <v-list-item title="Password"
                subtitle="Require password for purchase or use password to restrict purchase"></v-list-item>
            </v-list>
            <v-divider></v-divider>
            <v-list lines="two" subheader>
              <v-list-subheader>General</v-list-subheader>
              <v-list-item title="Notifications" subtitle="Notify me about updates to apps or games that I downloaded">
                <template v-slot:prepend>
                  <v-checkbox v-model="notifications"></v-checkbox>
                </template>
              </v-list-item>
              <v-list-item title="Sound" subtitle="Auto-update apps at any time. Data charges may apply">
                <template v-slot:prepend>
                  <v-checkbox v-model="sound"></v-checkbox>
                </template>
              </v-list-item>
              <v-list-item title="Auto-add widgets" subtitle="Automatically add home screen widgets">
                <template v-slot:prepend>
                  <v-checkbox v-model="widgets"></v-checkbox>
                </template>
              </v-list-item>
            </v-list>
          </v-card>
        </v-dialog>
      </v-row> -->
      <!-- </template> -->
      

  <v-card>
    <v-tabs
      v-model="tab"
      bg-color=""
      centered
      
    >
      <v-tab value="tab-1">
        <v-icon>mdi-phone</v-icon>
        Recents
      </v-tab>

      <v-tab value="tab-2">
        <v-icon>mdi-heart</v-icon>
        Favorites
      </v-tab>

      <v-tab value="tab-3">
        <v-icon>mdi-account-box</v-icon>
        Nearby
      </v-tab>
    </v-tabs>

    <v-window v-model="tab">
      <v-window-item
        v-for="i in 3"
        :key="i"
        :value="'tab-' + i"
      >
        <v-card>
          <v-card-text>{{ text }}</v-card-text>
        </v-card>
      </v-window-item>

    </v-window>
  </v-card>


  
  <v-data-table-virtual
    :headers="headers"
    :items="virtualDesserts"
    class="elevation-1"
    height="400"
    item-value="name"
  ></v-data-table-virtual>

  <v-container>
    <v-row>
      <v-col cols="12" md="6">
        <v-skeleton-loader
          class="mx-auto border"
          max-width="300"
          type="card-avatar, actions"
        ></v-skeleton-loader>
      </v-col>

      <v-col cols="12" md="6">
        <v-skeleton-loader
          class="mx-auto border"
          max-width="300"
          type="image, article"
        ></v-skeleton-loader>
      </v-col>
    </v-row>
  </v-container>
  

  <v-sheet class="flex-1-1-100 ma-2 pa-2">
      <v-bottom-navigation grow>
  <v-btn value="recent">
    <v-icon>mdi-history</v-icon>

    Mensagens
  </v-btn>

  <v-btn value="favorites">
    <v-icon>mdi-phone</v-icon>

    Chamadas
  </v-btn>

  <v-btn value="nearby">
    <v-icon>mdi-whatsapp</v-icon>

    WhatsApp
  </v-btn>
</v-bottom-navigation>
    </v-sheet>

      <router-view>

      </router-view>
    </v-main>

    <v-footer>2023 — Bissonde, LLC</v-footer>
  </v-app>
</template>


<script setup>
import { ref } from 'vue'
const drawer = ref(false)
</script>

<script>
export default {
  data: () => ({
    drawer: false,
    searchText: null,
    search: null,
    searchClosed: true,
    searchValue: null,
    dialog: false,
    imgsrc: "",
    btntext: "Show Image",
    isLoaded: false,
    isLoading: false,
    lorem: `Lorem ipsum dolor sit amet, mel at clita quando. Te sit oratio vituperatoribus, nam ad ipsum posidonium mediocritatem, explicari dissentiunt cu mea. Repudiare disputationi vim in, mollis iriure nec cu, alienum argumentum ius ad. Pri eu justo aeque torquatos.`,
    itemsM: [
      { text: 'Home', icon: 'mdi-view-dashboard', to: '/' },
      { text: 'Contactos', icon: 'mdi-account', to: 'contacts' },
      { text: 'Grupos', icon: 'mdi-account-group', to: 'groups' },
      { text: 'Campanhas', icon: 'mdi-account-voice', to: 'campaigns' },
      { text: 'Agendamento', icon: 'mdi-account-clock', to: 'calendar' },
      { text: 'Mensagem', icon: 'mdi-message-plus', to: 'message' },
      { text: 'Chamadas', icon: 'mdi-phone-settings', to: 'calls' },
      { text: 'WhatsApp', icon: 'mdi-whatsapp', to: 'whatsapp' },
      { text: 'E-mail', icon: 'mdi-email-fast-outline', to: 'email' },
      { text: 'Histórico', icon: 'mdi-history', to: 'history' },
      { text: 'Configuarções', icon: 'mdi-cog', to: 'settings' },
    ],
    tabMenus: [
      { text: 'Dashboard', icon: 'mdi-view-dashboard', to: '/' },
      { text: 'Contactos', icon: 'mdi-account', to: 'contacts' },
      { text: 'Grupos', icon: 'mdi-account-group', to: 'groups' },
      { text: 'Campanhas', icon: 'mdi-account-voice', to: 'campaigns' },
      { text: 'Agendamento', icon: 'mdi-account-clock', to: 'calendar' },
      { text: 'Mensagem', icon: 'mdi-message-plus', to: 'message' },
      { text: 'Chamadas', icon: 'mdi-phone-settings', to: 'calls' },
      { text: 'WhatsApp', icon: 'mdi-whatsapp', to: 'whatsapp' },
      { text: 'E-mail', icon: 'mdi-email-fast-outline', to: 'email' },
      { text: 'Histórico', icon: 'mdi-history', to: 'history' },
      { text: 'Configuarções', icon: 'mdi-cog', to: 'settings' }
    ],
    tab: null,
     model: null,
        text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.',
    labels: { 0: 'SU', 1: 'MO', 2: 'TU', 3: 'WED', 4: 'TH', 5: 'FR', 6: 'SA' },
    expand: false,
    time: 0,
    forecast: [
      { day: 'Tuesday', icon: 'mdi-white-balance-sunny', temp: '24\xB0/12\xB0' },
      { day: 'Wednesday', icon: 'mdi-white-balance-sunny', temp: '22\xB0/14\xB0' },
      { day: 'Thursday', icon: 'mdi-cloud', temp: '25\xB0/15\xB0' },
    ],
    cards: [
      // { title: 'Pre-fab homes', src: 'https://cdn.vuetifyjs.com/images/cards/house.jpg', flex: 12 },
      { title: 'Favorite road trips', src: 'https://cdn.vuetifyjs.com/images/cards/road.jpg', flex: 6 },
      // { title: 'Best airlines', src: 'https://cdn.vuetifyjs.com/images/cards/plane.jpg', flex: 6 },
      // { title: 'Best airlines', src: 'https://cdn.vuetifyjs.com/images/cards/plane.jpg', flex: 6 },
      { title: 'Favorite road trips', src: 'https://cdn.vuetifyjs.com/images/cards/road.jpg', flex: 6 },
      { title: 'Favorite road trips', src: 'https://cdn.vuetifyjs.com/images/cards/road.jpg', flex: 6 },
      { title: 'Favorite road trips', src: 'https://cdn.vuetifyjs.com/images/cards/road.jpg', flex: 6 },
    ],
    itemss: [
      { title: 'Meu Perfil', icon: 'mdi-account' },
      { title: 'Configurações', icon: 'mdi-cog' },
      { title: 'Terminar Sessão', icon: 'mdi-logout' },
      { title: 'Convidar', icon: 'mdi-account-plus' }
    ],
    headers: [
        {
          title: 'Dessert (100g serving)',
          align: 'start',
          sortable: false,
          key: 'name',
        },
        { title: 'Calories', align: 'end', key: 'calories' },
        { title: 'Fat (g)', align: 'end', key: 'fat' },
        { title: 'Carbs (g)', align: 'end', key: 'carbs' },
        { title: 'Protein (g)', align: 'end', key: 'protein' },
        { title: 'Iron (%)', align: 'end', key: 'iron' },
      ],
      desserts: [
        {
          name: 'Frozen Yogurt',
          calories: 159,
          fat: 6.0,
          carbs: 24,
          protein: 4.0,
          iron: '1',
        },
        {
          name: 'Ice cream sandwich',
          calories: 237,
          fat: 9.0,
          carbs: 37,
          protein: 4.3,
          iron: '1',
        },
        {
          name: 'Eclair',
          calories: 262,
          fat: 16.0,
          carbs: 23,
          protein: 6.0,
          iron: '7',
        },
        {
          name: 'Cupcake',
          calories: 305,
          fat: 3.7,
          carbs: 67,
          protein: 4.3,
          iron: '8',
        },
        {
          name: 'Gingerbread',
          calories: 356,
          fat: 16.0,
          carbs: 49,
          protein: 3.9,
          iron: '16',
        },
        {
          name: 'Jelly bean',
          calories: 375,
          fat: 0.0,
          carbs: 94,
          protein: 0.0,
          iron: '0',
        },
        {
          name: 'Lollipop',
          calories: 392,
          fat: 0.2,
          carbs: 98,
          protein: 0,
          iron: '2',
        },
        {
          name: 'Honeycomb',
          calories: 408,
          fat: 3.2,
          carbs: 87,
          protein: 6.5,
          iron: '45',
        },
        {
          name: 'Donut',
          calories: 452,
          fat: 25.0,
          carbs: 51,
          protein: 4.9,
          iron: '22',
        },
        {
          name: 'KitKat',
          calories: 518,
          fat: 26.0,
          carbs: 65,
          protein: 7,
          iron: '6',
        },
      ]
  }),

  methods: {
    greet() {
      alert(`Hello !` + this.searchValue)
    },
    loaded() {
      this.isLoaded = true;
      this.isLoading = false;
    },
    toggleimg: function () {
      if (this.imgsrc == "") {
        this.isLoaded = false;
        this.isLoading = true;
        this.imgsrc = "https://images2.alphacoders.com/103/1039991.jpg"
        this.btntext = "Hide Image"
      } else {
        this.imgsrc = ""
        this.btntext = "Show Image"
      }
    }
  },
  computed: {
      virtualDesserts () {
        return [...Array(10000).keys()].map(i => {
          const dessert = { ...this.desserts[i % 10] }
          dessert.name = `${dessert.name} #${i}`

          return dessert
        })
      }
    }
}
</script>


<style lang="sass">
  .v-input.expanding-search
    height:55px
    transition: max-width 0.3s
    .v-field__outline
      &:before, &:after
        cursor: pointer
        border-color: transparent !important         
    &.closed  
        max-width: 43px
        .v-field__outline
          background: transparent !important
</style>

<style scoped>
.dialog-bottom-transition-enter-active,
.dialog-bottom-transition-leave-active {
  transition: transform .9s ease-in-out;
}

.v-text-field {
  color: white !important;
  /* this will override the existing property applied */
  /* add whatever properties you want */

}
</style>