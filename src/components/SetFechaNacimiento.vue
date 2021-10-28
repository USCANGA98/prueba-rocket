<template>
  <div>
    <v-card color="grey lighten-3" flat>
      <div class="container">
        <p style="font-weight: 600; font-size: 20px">
          ¿Cuál es tu fecha de nacimiento?
        </p>
        <v-form @input="enviarFecha">
          <v-text-field label="Dia" outlined v-model="data.dia"> </v-text-field>
          <v-text-field class="my-n4" label="Mes" outlined v-model="data.mes">
          </v-text-field>
          <v-text-field class="my-n4" label="Año" outlined v-model="data.año">
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
        dia: "",
        mes: "",
        año: "",
      },
    };
  },
  methods: {
    enviarFecha() {
      this.$emit("fecha", this.data);
    },
  },
};
</script>

<style lang="scss" scoped>
</style>