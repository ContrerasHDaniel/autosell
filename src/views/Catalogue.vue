<template>
  <v-app id="inspire">
    <v-app-bar
      id="navbar"
      app
      dark
      shrink-on-scroll
      src="https://cdn.pixabay.com/photo/2019/05/01/03/45/car-4169975_960_720.jpg"
      fade-img-on-scroll
      >
        <template v-slot:img="{ props }">
          <v-img
            v-bind="props"
            gradient="to top right, rgba(251,251,242,.7), rgba(100, 182, 172,1)"
          ></v-img>
        </template>
        <v-spacer></v-spacer>
        <v-text-field
          class="nav-search"
          label="Buscar"
          placeholder="Escribe marca, modelo, año, color..."
          append-icon="fa-search"
          outlined
          dense
        >
        </v-text-field>
        <v-spacer></v-spacer>
      <v-app-bar-nav-icon></v-app-bar-nav-icon>
    </v-app-bar>

    <v-navigation-drawer app width="20rem">
      <v-sheet color="lighten-4" class="pa-4">
        <div>AutoSell</div>
      </v-sheet>

      <v-divider></v-divider>
      <template>
        <v-card elevation="0" class="mx-auto">
          <v-row>
            <v-expansion-panels
              v-model="panel"
              :disabled="disabled"
              multiple
            >
              <v-expansion-panel expand class="brand-expand">
                <v-expansion-panel-header>Marca</v-expansion-panel-header>
                <v-expansion-panel-content class="overflow-y">
                  <v-container>
                    <v-row>
                      <template v-for="n in 35">
                        <v-col
                          :key="n"
                          class="brand-name"
                          cols="3"
                        >
                          <v-sheet height="23">
                            <v-img
                              position="center"
                              src="https://i.pinimg.com/originals/93/89/6e/93896e3a2490b4fac021c8d6c705c248.png"
                            >
                              <span class="brand-span">Mercedes Benz</span>
                            </v-img>
                          </v-sheet>
                        </v-col>
                      </template>
                    </v-row>
                  </v-container>
                </v-expansion-panel-content>
              </v-expansion-panel>
            </v-expansion-panels>
          </v-row>
        </v-card>
      </template>
      <template>
        <v-container fluid>
          <v-row>
            <v-col cols="12">
              <v-combobox
                :items="items"
                label="Busca por modelos"
                multiple
                chips
              >
              </v-combobox>
            </v-col>
          </v-row>
        </v-container>
      </template>
      <template>
        <v-card class="mx-auto">
          <v-card-text class="card-title text-left">
            <div>Año</div>
          </v-card-text>
          <v-row>
            <template v-for="n in 8">
              <v-col
                :key="n"
                cols="4"
              >
                <v-btn class="year-btn" elevation="2">2999</v-btn>
              </v-col>
            </template>
          </v-row>
        </v-card>
      </template>
      <template>
        <v-card class="mx-auto">
          <v-card-text class="card-title text-left">
            <div>Precio</div>
          </v-card-text>
          <v-row>
            <v-col cols="6">
              <v-text-field
                v-model="price[0]"
                class="mt-0"
                hide-details
                single-line
              ></v-text-field>
            </v-col>
            <v-col cols="6">
              <v-text-field
                v-model="price[1]"
                class="mt-0"
                hide-details
                single-line
              ></v-text-field>
            </v-col>
          </v-row>
          <v-range-slider
            v-model="price"
            :max="900000"
            :min="80000"
            :step="10"
            tick-size="2"
          ></v-range-slider>
        </v-card>
      </template>
      <template>
        <v-card class="mx-auto">
          <v-card-text class="card-title text-left">
            <div>Kilometraje</div>
          </v-card-text>
          <v-row>
            <v-col cols="6">
              <v-text-field
                v-model="kilometers[0]"
                class="mt-0"
                hide-details
                single-line
              ></v-text-field>
            </v-col>
            <v-col cols="6">
              <v-text-field
                v-model="kilometers[1]"
                class="mt-0"
                hide-details
                single-line
              ></v-text-field>
            </v-col>
          </v-row>
          <v-range-slider
            v-model="kilometers"
            :max="200000"
            :min="1000"
            :step="10"
            tick-size="2"
          ></v-range-slider>
        </v-card>
      </template>
      <template>
        <v-card>
          <v-container fluid>
            <v-row>
              <v-col
                class="d-flex"
              >
                <v-select
                  class="select-trans"
                  :items="selectItems"
                  label="Transmisión"
                  outlined
                ></v-select>
              </v-col>
            </v-row>
          </v-container>
        </v-card>
      </template>
      <template>
        <v-card class="mx-auto">
          <v-card-text class="card-title text-left">
            <div>Tipo</div>
          </v-card-text>
          <v-container>
            <v-row>
              <template v-for="n in 8" >
                <v-col
                  :key="n"
                  cols="3"
                >
                  <v-img
                    src="https://cdn.iconscout.com/icon/premium/png-256-thumb/car-1529-667436.png"
                    max-height="32px"
                  ></v-img>
                </v-col>
              </template>
            </v-row>
          </v-container>
        </v-card>
      </template>
      <template>
        <v-card>
          <v-card-text class="card-title text-left">
            <div>Color</div>
          </v-card-text>
          <v-container>
            <v-row>
              <template v-for="n in 15">
                <v-col
                  :key="n"
                  cols="3"
                >
                  <v-icon
                    x-large
                  >mdi-access-point</v-icon>
                </v-col>
              </template>
            </v-row>
          </v-container>
        </v-card>
      </template>
    </v-navigation-drawer>

    <v-main class="grey lighten-2 overflow-auto">
      <v-container class="py-8 px-6"
        fluid>
        <v-row>
          <template v-for="n in 24">
            <v-col
              :key="n"
              class="mt-2"
              cols="4"
            >
              <v-sheet height="250"></v-sheet>
            </v-col>
          </template>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
export default {
  data: () => ({
    panel: [0, 1],
    disabled: false,
    readonly: false,
    items: [
      'Mazda',
      'Toyota',
      'Mercedes Benz',
      'Acura',
      'Alfa Romeo',
      'Volkswagen',
      'Nissan',
      'Cadillac',
      'Audi',
      'Jeep',
    ],
    slider: 45,
    volume: 10,
    price: [80000, 900000],
    kilometers: [1000, 200000],
    selectItems: [
      'Todas',
      'Automática',
      'Manual',
    ],
  }),
};
</script>

<style lang="scss" scoped>

.nav-search {
  margin-top: 0.5rem;
  font-weight: 400;
}

#navbar {
  background-color: #64B6AC;
}

.brand-span {
  align-content: center;
  text-align: center;
  font-size: 0.6rem;
  font-weight: 700;
  margin-right: 0;
  color: #5d737e;
}

.year-btn {
  width: inherit;
}

.card-title {
  padding-bottom: 2px;
}

.select-trans {
  height: 70px;
}

.subtitle {
  font-size: 0.6rem;
}
</style>
