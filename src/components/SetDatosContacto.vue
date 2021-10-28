<template>
  <div>
    <v-card color="grey lighten-3" flat>
      <div class="container">
        <p style="font-weight: 600; font-size: 20px">Datos de contacto</p>
        <v-form @input="enviarContacto">
          <v-text-field
            v-model="data.correo"
            label="Correo electrónico"
            outlined
          >
          </v-text-field>
          <v-text-field
            v-model="data.telefono"
            class="my-n4"
            label="Teléfono celular"
            outlined
          >
          </v-text-field>
        </v-form>
      </div>
    </v-card>
  </div>
</template>

<script>
export default {
  data() {
    return {
      data: {
        correo: "",
        telefono: "",
      },
    };
  },
  methods: {
    enviarContacto() {
      this.$emit("contacto", this.data);
    },
  },
};
</script>

<style lang="scss" scoped>
</style>