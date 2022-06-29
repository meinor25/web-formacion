<template>
  <div class="services" id="services">
    <v-container fluid height="100vh">
      <v-carousel
        show-arrows-on-hover
        cycle
        hide-delimiter-background
        height="600"
        class="pt-5 d-flex align-center"
      >
        <v-carousel-item v-for="(slide, i) in sliders" :key="i" class="pt-15">
          <v-row class="pt-10 px-15">
            <v-col cols="12" md="6" align-self="center">
              <div class="d-flex justify-center">
                <v-img
                  :src="slide.img"
                  class="rounded-pill"
                  :max-width="$vuetify.breakpoint.lgAndUp ? '500' : '400'"
                >
                </v-img>
              </div>
            </v-col>
            <v-col
              cols="12"
              md="6"
              class="text-center mb-6"
              align-self="center"
            >
              <h2 class="text-h6 text-md-h4 font-weight-bold green--text">
                {{ slide.title }}
              </h2>
              <p class="text-subtitle-2 text-md-body-1 px-10">
                {{ slide.message }}
              </p>
            </v-col>
          </v-row>
        </v-carousel-item>
      </v-carousel>
    </v-container>
  </div>
</template>

<script>
export default {
  name: "Services",
  data() {
    return {
      sliders: [
        {
          title: "Servicio de fabricación",
          img: require("../assets/service-1.jpg"),
          message:
            "gracias a los diferentes filamentos como, Filamento PLA, Filamento ABS, Filamento PETG, Filamento PC, entre otros filamentos, será posible crear casi cualquier producto u objetos, incluso productos personales al estilo del cliente, algo que le permite al cliente contar con un producto personal, único y dificil de hallar de otro lugar.",
        },
        {
          title: "Servicio de reparacion",
          img: require("../assets/service-2.jpg"),
          message:
            "Gracias a nuestra capacidad de fabricación, también nos brinda la capacidad de arreglar, complementar, y renovar todo tipo de productos, gracias a la infinidad de repuestos y soluciones y materiales que podemos crear, no habrá mucho limites en esta área ya que con las impresoras 3D podeos crear desde complementos específicos, hasta rediseñar productos.",
        },
        {
          title: "Venta de repuestos",
          img: require("../assets/service-3.jpg"),
          message:
            "tenemos la capacidad de crear repuestos específicos que en ocasiones las personas necesitan pero que se vuelven difíciles de hallar o poder solicitar. Desde cosas pequeñas como, tapas de controles, carcasas de computadoras, tapas de envases, hasta algo más demandado como partes de sillas de oficina y partes de auto.",
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped></style>
