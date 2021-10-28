<template>
  <div>
    
      <v-app-bar
        color="#F660FF"
        dark
        shrink-on-scroll
        prominent
        fade-img-on-scroll
        scroll-target="#scrolling-techniques-5"
      >
        <v-app-bar-nav-icon></v-app-bar-nav-icon>

        <v-app-bar-title>Encuesta <v-icon>mdi-clock-fast</v-icon></v-app-bar-title>

        <v-spacer></v-spacer>

        <v-btn icon>
          <v-icon>mdi-magnify</v-icon>
        </v-btn>

        <v-btn icon>
          <v-icon>mdi-heart</v-icon>
        </v-btn>

        <v-btn icon>
          <v-icon>mdi-dots-vertical</v-icon>
        </v-btn>
      </v-app-bar>
      
    
  </div>
</template>

<script>
export default {
  data() {
    return {
      redes: [
        {
          title: "WhatsApp",
          icon: "mdi-whatsapp",
          color: "#00bb2d",
        },
        {
          title: "Facebook",
          icon: "mdi-facebook",
          color: "#3b5998",
        },
        {
          title: "Twitter",
          icon: "mdi-twitter",
          color: "#00acee",
        },
        {
          title: "Correo electrónico",
          icon: "mdi-email",
          color: "grey lighten-3",
        },
        {
          title: "Copiar enlace",
          icon: "mdi-link-variant",
          color: "grey lighten-3",
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
</style>