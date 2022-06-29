<template>
  <div class="footer">
    <v-footer color="black">
      <v-container>
        <v-row>
          <v-col
            class="white--text text-h6 d-flex align-center justify-center"
            cols="12"
            md="6"
          >
            <h3 class="mr-2"><Span>3D</Span> Earth</h3>
            <v-icon color="green">mdi-earth</v-icon>
          </v-col>
          <v-col class="white--text text-center">
            <v-row>
              <v-col class="d-flex justify-center">
                <v-icon color="white" class="px-5">mdi-whatsapp</v-icon>
                <v-icon color="white" class="px-5">mdi-facebook</v-icon>
                <v-icon color="white" class="px-5">mdi-instagram</v-icon>
              </v-col>
            </v-row>
          </v-col>
        </v-row>
      </v-container>
    </v-footer>
  </div>
</template>

<script>
export default {
  name: "Footer",
};
</script>

<style></style>
