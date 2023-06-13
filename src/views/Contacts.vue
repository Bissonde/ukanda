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

      <v-toolbar-title><v-icon>mdi-account</v-icon>&nbsp;Contactos</v-toolbar-title>


      <!-- <v-spacer></v-spacer> -->

      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>


      <v-col cols="auto">
        <v-btn density="compact" icon="mdi-plus" color="white"></v-btn>
      </v-col>
    </v-app-bar>

    <v-main>
      <!--  -->

  <v-row justify="center">
    <v-dialog
      v-model="dialog"
      persistent
      width="1024"
    >
      <template v-slot:activator="{ props }">
        <div style="height: 50px;"></div>
        <!-- <v-spacer></v-spacer>
         -->
        <v-btn
          color="primary"
          v-bind="props"
        >
          Open Dialog
        </v-btn>
      </template>
      <v-card>
        <v-card-title>
          <span class="text-h5">User Profile</span>
        </v-card-title>
        <v-card-text>
          <v-container>
            <v-row>
              <v-col
                cols="12"
                sm="6"
                md="4"
              >
                <v-text-field
                  label="Legal first name*"
                  required
                ></v-text-field>
              </v-col>
              <v-col
                cols="12"
                sm="6"
                md="4"
              >
                <v-text-field
                  label="Legal middle name"
                  hint="example of helper text only on focus"
                ></v-text-field>
              </v-col>
              <v-col
                cols="12"
                sm="6"
                md="4"
              >
                <v-text-field
                  label="Legal last name*"
                  hint="example of persistent helper text"
                  persistent-hint
                  required
                ></v-text-field>
              </v-col>
              <v-col cols="12">
                <v-text-field
                  label="Email*"
                  required
                ></v-text-field>
              </v-col>
              <v-col cols="12">
                <v-text-field
                  label="Password*"
                  type="password"
                  required
                ></v-text-field>
              </v-col>
              <v-col
                cols="12"
                sm="6"
              >
                <v-select
                  :items="['0-17', '18-29', '30-54', '54+']"
                  label="Age*"
                  required
                ></v-select>
              </v-col>
              <v-col
                cols="12"
                sm="6"
              >
                <v-autocomplete
                  :items="['Skiing', 'Ice hockey', 'Soccer', 'Basketball', 'Hockey', 'Reading', 'Writing', 'Coding', 'Basejump']"
                  label="Interests"
                  multiple
                ></v-autocomplete>
              </v-col>
            </v-row>
          </v-container>
          <small>*indicates required field</small>
        </v-card-text>
        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn
            color="blue-darken-1"
            variant="text"
            @click="dialog = false"
          >
            Close
          </v-btn>
          <v-btn
            color="blue-darken-1"
            variant="text"
            @click="dialog = false"
          >
            Save
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </v-row>
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
      dialog: false,
  }),
}
</script>

