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


      <v-btn icon  color="white">
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
      <template>
  <v-container grid-list-md text-xs-center>
    <v-layout row wrap>
      <v-flex xs12>
        <v-card dark color="primary">
          <v-card-text class="px-0">12</v-card-text>
        </v-card>
      </v-flex>
      <v-flex v-for="i in 2" :key="`6${i}`" xs6>
        <v-card dark color="secondary">
          <v-card-text class="px-0">6</v-card-text>
        </v-card>
      </v-flex>
      <v-flex v-for="i in 3" :key="`4${i}`" xs4>
        <v-card dark color="primary">
          <v-card-text class="px-0">4</v-card-text>
        </v-card>
      </v-flex>
      <v-flex v-for="i in 4" :key="`3${i}`" xs3>
        <v-card dark color="secondary">
          <v-card-text class="px-0">3</v-card-text>
        </v-card>
      </v-flex>
      <v-flex v-for="i in 6" :key="`2${i}`" xs2>
        <v-card dark color="primary">
          <v-card-text class="px-0">2</v-card-text>
        </v-card>
      </v-flex>
      <v-flex v-for="i in 12" :key="`1${i}`" xs1>
        <v-card dark color="secondary">
          <v-card-text class="px-0">1</v-card-text>
        </v-card>
      </v-flex>
    </v-layout>
  </v-container>
</template>




      <v-container>
        <v-data-table :headers="headers" :items="desserts" class="elevation-1">
          <template v-slot:items="props">
            <td>{{ props.item.name }}</td>
            <td class="text-xs-right">{{ props.item.calories }}</td>
            <td class="text-xs-right">{{ props.item.fat }}</td>
            <td class="text-xs-right">{{ props.item.carbs }}</td>
            <td class="text-xs-right">{{ props.item.protein }}</td>
            <td class="text-xs-right">{{ props.item.iron }}</td>
          </template>
        </v-data-table>
      </v-container>

      <!-- <template> -->
      <v-row justify="center">
        <v-dialog v-model="dialog" fullscreen :scrim="false" transition="dialog-bottom-transition">
          <template v-slot:activator="{ props }">
            <v-btn color="primary" dark v-bind="props">
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
      </v-row>
      <!-- </template> -->

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
    rowsPerPageItems: [4, 8, 12],
      pagination: {
        rowsPerPage: 4
      },
      items: [
        {
          name: 'Frozen Yogurt',
          calories: 159,
          fat: 6.0,
          carbs: 24,
          protein: 4.0,
          sodium: 87,
          calcium: '14%',
          iron: '1%'
        },
        {
          name: 'Ice cream sandwich',
          calories: 237,
          fat: 9.0,
          carbs: 37,
          protein: 4.3,
          sodium: 129,
          calcium: '8%',
          iron: '1%'
        },
        {
          name: 'Eclair',
          calories: 262,
          fat: 16.0,
          carbs: 23,
          protein: 6.0,
          sodium: 337,
          calcium: '6%',
          iron: '7%'
        },
        {
          name: 'Cupcake',
          calories: 305,
          fat: 3.7,
          carbs: 67,
          protein: 4.3,
          sodium: 413,
          calcium: '3%',
          iron: '8%'
        }
      ],
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
    itemss: [
      { title: 'Meu Perfil', icon: 'mdi-account' },
      { title: 'Configurações', icon: 'mdi-cog' },
      { title: 'Terminar Sessão', icon: 'mdi-logout' },
      { title: 'Convidar', icon: 'mdi-account-plus' }
    ],
    headers: [
      {
        text: 'Dessert (100g serving)',
        align: 'left',
        sortable: false,
        value: 'name'
      },
      { text: 'Calories', value: 'calories' },
      { text: 'Fat (g)', value: 'fat' },
      { text: 'Carbs (g)', value: 'carbs' },
      { text: 'Protein (g)', value: 'protein' },
      { text: 'Iron (%)', value: 'iron' }
    ],
    desserts: [
      {
        name: 'Frozen Yogurt',
        calories: 159,
        fat: 6.0,
        carbs: 24,
        protein: 4.0,
        iron: '1%'
      },
      {
        name: 'Ice cream sandwich',
        calories: 237,
        fat: 9.0,
        carbs: 37,
        protein: 4.3,
        iron: '1%'
      },
      {
        name: 'Eclair',
        calories: 262,
        fat: 16.0,
        carbs: 23,
        protein: 6.0,
        iron: '7%'
      },
      {
        name: 'Cupcake',
        calories: 305,
        fat: 3.7,
        carbs: 67,
        protein: 4.3,
        iron: '8%'
      },
      {
        name: 'Gingerbread',
        calories: 356,
        fat: 16.0,
        carbs: 49,
        protein: 3.9,
        iron: '16%'
      },
      {
        name: 'Jelly bean',
        calories: 375,
        fat: 0.0,
        carbs: 94,
        protein: 0.0,
        iron: '0%'
      },
      {
        name: 'Lollipop',
        calories: 392,
        fat: 0.2,
        carbs: 98,
        protein: 0,
        iron: '2%'
      },
      {
        name: 'Honeycomb',
        calories: 408,
        fat: 3.2,
        carbs: 87,
        protein: 6.5,
        iron: '45%'
      },
      {
        name: 'Donut',
        calories: 452,
        fat: 25.0,
        carbs: 51,
        protein: 4.9,
        iron: '22%'
      },
      {
        name: 'KitKat',
        calories: 518,
        fat: 26.0,
        carbs: 65,
        protein: 7,
        iron: '6%'
      }
    ]
  }),

  methods: {
    greet() {
      alert(`Hello !` + this.searchValue)
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