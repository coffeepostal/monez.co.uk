<template>
  <v-app id="inspire">
    <v-navigation-drawer v-model="drawer" app clipped temporary>
      <v-list dense>
        <v-list-item @click>
          <v-list-item-action>
            <v-icon>mdi-view-dashboard</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Neural Net Worth</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item @click>
          <v-list-item-action>
            <v-icon>mdi-settings</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>About</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar app clipped-left>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
      <v-toolbar-title>MONEZ.co.uk</v-toolbar-title>
    </v-app-bar>

    <v-content>
      <v-container class="fill-height" fluid>
        <v-row align="center" justify="center">
          <v-col>
            <v-simple-table :dense="dense" :fixed-header="fixedHeader">
              <template v-slot:default>
                <thead>
                  <tr>
                    <th class="text-left">Name</th>
                    <th class="text-left">Neural Net Worth</th>
                  </tr>
                </thead>
                <tbody>
                  <tr v-for="item in familes" :key="item.name">
                    <td>{{ item.name }}</td>
                    <td>£{{ item.netWorth }}</td>
                  </tr>
                </tbody>
              </template>
            </v-simple-table>
          </v-col>
        </v-row>
      </v-container>
    </v-content>

    <v-footer app>
      <span>&copy; 2019</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  props: {
    source: String
  },

  data: () => ({
    drawer: null,
    dense: false,
    fixedHeader: false,
    height: 600,
    familes: [
      {
        name: "Alforithm (Family)",
        netWorth: "237,000.00"
      },
      {
        name: "Algodrithm, Ma Sheen Lurning",
        netWorth: "159,000.00"
      },
      {
        name: "Algodrithm, Sir Chingin",
        netWorth: "123,000.00"
      },
      {
        name: "Greenrithm, Al",
        netWorth: "262,000.00"
      },
      {
        name: "Godrithm, Albert",
        netWorth: "305,000.00"
      },
      {
        name: "Rithm, Dr. Al God",
        netWorth: "145,000.00"
      }
    ]
  }),

  created() {
    this.$vuetify.theme.dark = true;
  }
};
</script>