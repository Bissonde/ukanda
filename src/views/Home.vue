<template>
  <v-app id="inspire">
    <v-navigation-drawer v-model="drawer">
      <!--  -->
      <v-list-subheader>&nbsp;&nbsp;&nbsp;MENU</v-list-subheader>
      <v-card>
        <v-layout>
          <v-navigation-drawer floating permanent>
            <v-list density="compact" nav>
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
            </v-list>
          </v-navigation-drawer>
          <v-main style="height: 750px"></v-main>
        </v-layout>
      </v-card>
    </v-navigation-drawer>

    <v-app-bar color="primary">
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

      <v-toolbar-title>uKanda</v-toolbar-title>


      <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>


      <v-btn icon>
        <v-icon>mdi-dots-vertical</v-icon>
      </v-btn>
    </v-app-bar>

    <v-main>
      <!--  -->
      
    <v-tabs
      v-model="tab"
      background-color="transparent"
      color="basil"
      grow
    >
      <v-tab
        v-for="item in items"
        :key="item"
      >
        {{ item }}
      </v-tab>
    </v-tabs>

    
    <v-tabs-items v-model="tab">
      <v-tab-item
        v-for="item in items"
        :key="item"
      >
        <v-card
          color="basil"
          flat
        >
          <v-card-text>{{ text }}</v-card-text>
        </v-card>
      </v-tab-item>
    </v-tabs-items>
    </v-main>
  </v-app>

  <v-footer class="d-flex flex-column">
    <div class="bg-teal d-flex w-100 align-center px-4">
      <strong>Get connected with us on social networks!</strong>

      <v-spacer></v-spacer>

      <v-btn v-for="icon in icons" :key="icon" class="mx-4" :icon="icon" variant="plain" size="small"></v-btn>
    </div>

    <div class="px-4 py-2 bg-black text-center w-100">
      {{ new Date().getFullYear() }} — <strong>Vuetify</strong>
    </div>
  </v-footer>
</template>

<script setup>
import { ref } from 'vue'
const drawer = ref(false)
</script>

<script>
export default {
  data: () => ({ drawer: false }),
}
</script>

