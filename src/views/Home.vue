<template>
  <v-app :style="{ background: $vuetify.theme.themes.light.background }">
    <v-layout row>
      <v-flex md8>
        <v-app
          :style="{ background: $vuetify.theme.themes.dark.background }"
          class="rounded-tr-xl rounded-br-xl"
        >
          <v-container>
            <v-row>
              <v-col cols="12" sm="12">
                <v-app-bar color="rgba(0,0,0,0)" flat class="mx-8 mb-8 mt-3">
                  <v-text-field
                    prepend-icon="mdi-magnify"
                    color="teal"
                    placeholder="Recherchez vos symptômes"
                    flat
                    success
                  ></v-text-field>
                  <v-spacer></v-spacer>
                  <v-chip class="ma-2" color="white">
                    <v-icon left color="teal">
                      mdi-clock-time-nine
                    </v-icon>
                    30/12/2021
                  </v-chip>
                </v-app-bar>
              </v-col>
              <v-col cols="12" sm="12">
                <v-card
                  class="mx-12 rounded-tl-xl rounded-tr-xl rounded-bl-xl rounded-br-xl mt-n15"
                >
                  <v-list-item three-line>
                    <v-list-item-content class="pa-10">
                      <v-list-item-title class="headline mb-1">
                        Aujourd'hui
                        <span class="teal--text">-10%</span><br />
                        sur les examens des poumons
                      </v-list-item-title>
                      <v-list-item-subtitle>
                        Le prix du forfait comprend :<br />
                        La consultation d'un
                        pneumologue, spirographie et cardiogramme.
                        <span class="teal--text"></span>
                      </v-list-item-subtitle>
                    </v-list-item-content>

                    <v-list-item-avatar tile size="150" class="pr-10">
                      <img src="lungs.png" />
                    </v-list-item-avatar>
                  </v-list-item>
                </v-card>
              </v-col>
              <v-col cols="12" sm="12">
                <v-card
                  class="mx-12 rounded-tl-xl rounded-tr-xl rounded-bl-xl rounded-br-xl mt-n10"
                >
                  <v-app-bar color="rgba(0,0,0,0)" flat class="ma-8">
                    <h5>Statistiques de votre santé</h5>
                    <v-spacer></v-spacer>
                    <v-btn color="teal" text
                      >2021
                      <v-icon right>
                        mdi-chevron-down
                      </v-icon>
                    </v-btn>
                    <v-btn color="teal" rounded dark depressed>Année</v-btn>
                    <v-btn text>Mois</v-btn>
                  </v-app-bar>
                  <template>
                    <v-sparkline
                      :value="value"
                      color="teal"
                      :smooth="radius || false"
                      :padding="padding"
                      :line-width="width"
                      :stroke-linecap="lineCap"
                      :fill="fill"
                      :type="type"
                      :auto-line-width="autoLineWidth"
                      auto-draw
                    ></v-sparkline>
                  </template>
                </v-card>
              </v-col>
              <v-col cols="12" sm="6">
                <v-card
                  class="mx-12 rounded-tl-xl rounded-tr-xl rounded-bl-xl rounded-br-xl mt-n4"
                  color="teal"
                  dark
                >
                  <v-list-item three-line>
                    <v-list-item-content class="pa-2">
                      <v-list-item-title class="headline mb-1">
                        Rythme cardiaque <br />
                        <h2>70 bpm</h2>
                      </v-list-item-title>
                    </v-list-item-content>

                    <v-list-item-avatar tile size="150" class="pr-10">
                      <v-icon size="100">fas fa-heartbeat</v-icon>
                    </v-list-item-avatar>
                  </v-list-item>
                </v-card>

                <v-card
                  class="mx-12 rounded-tl-xl rounded-tr-xl rounded-bl-xl rounded-br-xl mt-7"
                  color="teal"
                  dark
                >
                  <v-list-item three-line>
                    <v-list-item-content class="pa-2">
                      <v-list-item-title class="headline mb-1">
                        Tension arterielle <br />
                        <h2>14/8</h2>
                      </v-list-item-title>
                    </v-list-item-content>

                    <v-list-item-avatar tile size="150" class="pr-10">
                      <v-icon size="100">fas fa-procedures</v-icon>
                    </v-list-item-avatar>
                  </v-list-item>
                </v-card>
              </v-col>
              <v-col cols="12" sm="6">
                <v-card
                  class="mx-12 rounded-tl-xl rounded-tr-xl rounded-bl-xl rounded-br-xl mt-n12"
                >
                  <v-app-bar color="rgba(0,0,0,0)" flat class="ma-8">
                    <h5>Votre activité</h5>
                    <v-spacer></v-spacer>
                    <v-btn color="teal" rounded dark depressed>Semaine</v-btn>
                    <v-btn text>Mois</v-btn>
                  </v-app-bar>
                  <v-progress-circular
                    rotate="360"
                    size="100"
                    width="15"
                    value="50"
                    color="teal"
                    class="mt-n5 ml-5 mb-2"
                  >
                    50
                  </v-progress-circular>
                  <v-progress-circular
                    rotate="360"
                    size="100"
                    width="15"
                    value="70"
                    color="red"
                    class="mt-n5 ml-2 mb-2"
                  >
                    70
                  </v-progress-circular>
                  <v-progress-circular
                    rotate="360"
                    size="100"
                    width="15"
                    value="80"
                    color="blue"
                    class="mt-n5 ml-2 mb-2"
                  >
                    80
                  </v-progress-circular>
                </v-card>
                <v-card
                  class="mx-12 rounded-tl-xl rounded-tr-xl rounded-bl-xl rounded-br-xl mt-7"
                  color="teal"
                  dark
                >
                  <v-list-item three-line>
                    <v-list-item-content class="pa-2">
                      <v-list-item-title class="headline mb-1">
                        Saturation en oxygène <br />
                        <h2>98%</h2>
                      </v-list-item-title>
                    </v-list-item-content>

                    <v-list-item-avatar tile size="150" class="pr-10">
                      <v-icon size="100">fas fa-lungs</v-icon>
                    </v-list-item-avatar>
                  </v-list-item>
                </v-card>
              </v-col>
            </v-row>
          </v-container>
        </v-app>
      </v-flex>
      <v-flex md4>
        <v-app :style="{ background: $vuetify.theme.themes.light.background }">
          <v-container>
            <v-row>
              <v-col cols="12" sm="12">
                <v-list two-line>
                  <v-list-item>
                    <v-list-item-avatar>
                      <img src="https://media-exp1.licdn.com/dms/image/C5603AQGTPU2BF5Ktkg/profile-displayphoto-shrink_100_100/0/1619220866397?e=1644451200&v=beta&t=TCZ7QwWrFm-CR4u2wSQqAkiJzB4C_XjSvmJELmeDotw" />
                    </v-list-item-avatar>
                    <v-list-item-content>
                      <v-list-item-title>Sammy MERAZGA</v-list-item-title>
                      <v-list-item-subtitle class="teal--text"
                        >20 ans, Marseille</v-list-item-subtitle
                      >
                    </v-list-item-content>
                    <v-spacer></v-spacer>
                    <v-icon color="teal">mdi-menu</v-icon>
                  </v-list-item>
                </v-list>
              </v-col>
              <v-col cols="12" md="4">
                <v-row>
                  <v-col cols="12" md="2">
                    <v-card height="50px" width="10px" color="green"></v-card>
                  </v-col>
                  <v-col cols="12" md="10">
                    <v-list two-line subheader class="ml-n8">
                      <v-list-item>
                        <v-list-item-content>
                          <v-list-item-subtitle>Sang</v-list-item-subtitle>
                          <v-list-item-title>O+</v-list-item-title>
                        </v-list-item-content>
                      </v-list-item>
                    </v-list>
                  </v-col>
                </v-row>
              </v-col>
              <v-col cols="12" md="4">
                <v-row>
                  <v-col cols="12" md="2">
                    <v-card height="50px" width="10px" color="red"></v-card>
                  </v-col>
                  <v-col cols="12" md="10">
                    <v-list two-line subheader class="ml-n8">
                      <v-list-item>
                        <v-list-item-content>
                          <v-list-item-subtitle>Taille</v-list-item-subtitle>
                          <v-list-item-title>183 cm</v-list-item-title>
                        </v-list-item-content>
                      </v-list-item>
                    </v-list>
                  </v-col>
                </v-row>
              </v-col>
              <v-col cols="12" md="4">
                <v-row>
                  <v-col cols="12" md="2">
                    <v-card height="50px" width="10px" color="grey"></v-card>
                  </v-col>
                  <v-col cols="12" md="10">
                    <v-list two-line subheader class="ml-n8">
                      <v-list-item>
                        <v-list-item-content>
                          <v-list-item-subtitle>Poids</v-list-item-subtitle>
                          <v-list-item-title>67 kg</v-list-item-title>
                        </v-list-item-content>
                      </v-list-item>
                    </v-list>
                  </v-col>
                </v-row>
              </v-col>
              <v-col cols="12" sm="12">
                <v-btn text
                  >Décembre
                  <v-icon right>
                    mdi-chevron-down
                  </v-icon>
                </v-btn>
              </v-col>
              <v-col cols="12" sm="12">
                <v-list>
                  <v-list-item>
                    <v-item-content>
                      <v-btn class="mr-1" outlined color="teal darken-1"
                        >LUN</v-btn
                      >
                    </v-item-content>
                    <v-item-content>
                      <v-btn class="mr-1" outlined color="teal darken-1"
                        >MAR</v-btn
                      >
                    </v-item-content>
                    <v-item-content>
                      <v-btn class="mr-1" outlined color="teal darken-1"
                        >MER</v-btn
                      >
                    </v-item-content>
                    <v-item-content>
                      <v-btn class="mr-1" color="teal darken-1" dark>JEU</v-btn>
                    </v-item-content>
                    <v-item-content>
                      <v-btn class="mr-1" outlined color="teal darken-1"
                        >VEN</v-btn
                      >
                    </v-item-content>
                    <v-item-content>
                      <v-btn class="mr-1" outlined color="teal darken-1"
                        >SAM</v-btn
                      >
                    </v-item-content>
                  </v-list-item>
                </v-list>
              </v-col>
              <v-col cols="12" sm="12">
                <v-card
                  class="mx-12 rounded-tl-xl rounded-tr-xl rounded-bl-xl rounded-br-xl mt-n4 py-4"
                  color="teal"
                  dark
                  flat
                >
                  <v-list-item three-line>
                    <v-list-item-avatar tile size="30">
                      <v-icon size="30">mdi-tooth</v-icon>
                    </v-list-item-avatar>
                    <v-list-item-content class="pa-2">
                      <v-list-item-title class="headline mb-1">
                        Dentiste <br />
                        <h6>8:00 - 9:30</h6>
                        <h6>Dr. HUA</h6>
                      </v-list-item-title>
                    </v-list-item-content>
                  </v-list-item>
                </v-card>
              </v-col>
              <v-col cols="12" sm="12">
                <v-card
                  class="mx-12 rounded-tl-xl rounded-tr-xl rounded-bl-xl rounded-br-xl mt-n4 py-4"
                  color="teal lighten-5"
                  flat
                >
                  <v-list-item three-line>
                    <v-list-item-avatar tile size="30">
                      <v-icon size="30">fas fa-heartbeat</v-icon>
                    </v-list-item-avatar>
                    <v-list-item-content class="pa-2">
                      <v-list-item-title class="headline mb-1">
                        Cardiologue <br />
                        <h6>9:45 - 11:50</h6>
                        <h6>Dr. CLARK</h6>
                      </v-list-item-title>
                    </v-list-item-content>
                  </v-list-item>
                </v-card>
              </v-col>
              <v-col cols="12" sm="12">
                <v-btn text
                  >Votre Traitment
                  <v-icon right>
                    mdi-chevron-down
                  </v-icon>
                </v-btn>
              </v-col>
              <v-col cols="12" sm="12">
                <v-card
                  class="mx-12 rounded-tl-xl rounded-tr-xl rounded-bl-xl rounded-br-xl mt-n4 "
                  color="teal lighten-5"
                  flat
                >
                  <v-list-item three-line>
                    <v-list-item-avatar tile size="30">
                      <v-icon size="30" color="teal">mdi-pill</v-icon>
                    </v-list-item-avatar>
                    <v-list-item-content class="pa-2">
                      <v-list-item-title class="headline mb-1">
                        Paracétamol<br />
                        <h6>
                          <span class="teal--text">1 à 4 comprimés</span> par jour (si douleur)
                        </h6>
                      </v-list-item-title>
                    </v-list-item-content>
                  </v-list-item>
                </v-card>
              </v-col>
            </v-row>
          </v-container>
        </v-app>
      </v-flex>
    </v-layout>
  </v-app>
</template>
<script>
export default {
  data: () => ({
    width: 2,
    radius: 10,
    padding: 8,
    lineCap: "round",
    value: [0, 2, 5, 9, 5, 10, 3, 5, 0, 0, 1, 8, 2, 9, 0],
    fill: false,
    type: "trend",
    autoLineWidth: false,
  }),
  computed: {
    theme() {
      return this.$vuetify.theme.dark ? "dark" : "light";
    },
  },
};
</script>
<style scoped></style>
