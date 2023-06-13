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
                <v-list-item v-for="(item, i) in items" :key="i" :value="item" :to="item.to" color="primary" rounded="sm">

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

      <v-toolbar-title>uKanda</v-toolbar-title>


      <!-- <v-spacer></v-spacer> -->

      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>


      <v-btn icon>
        <v-icon>mdi-dots-vertical</v-icon>
      </v-btn>
    </v-app-bar>

    <v-main>
      <!--  -->
      <router-view></router-view>
    </v-main>
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
    items: [
      { text: 'Home', icon: 'mdi-view-dashboard', to: '/' },
      { text: 'Audience', icon: 'mdi-account', to: 'contacts' },
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
  }),
}
</script>

