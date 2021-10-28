<template>
  <div>
    <v-card color="grey lighten-3" flat>
      <div class="container">
        <p style="font-weight: 600; font-size: 20px">¿Cuál es tu nombre?</p>
        <v-form @input="enviarNombre">
          <v-text-field v-model="data.nombre" label="Nombre" outlined>
          </v-text-field>
          <v-text-field
            v-model="data.segundoNombre"
            class="my-n4"
            label="Segundo nombre"
            outlined
          >
          </v-text-field>
          <v-text-field
            v-model="data.apellidoPaterno"
            class="my-n4"
            label="Apellido paterno"
            outlined
          >
          </v-text-field>
          <v-text-field
            v-model="data.apellidoMaterno"
            class="my-n4"
            label="Apellido materno"
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
        nombre: "",
        segundoNombre: "",
        apellidoPaterno: "",
        apellidoMaterno: "",
      },
    };
  },
  methods: {
    enviarNombre() {
      this.$emit("nombre", this.data);
    },
  },
};
</script>

<style lang="scss" scoped>
</style>