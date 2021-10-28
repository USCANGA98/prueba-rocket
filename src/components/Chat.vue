<template>
  <v-container>
    <div style="width: 35%; margin: auto">
      <BarraNavegacion />
      <v-sheet
        color="grey lighten-5"
        id="scrolling-techniques-5"
        class="overflow-y-auto"
        max-height="600"
      >
        <v-container style="height: 400px">
          <v-row>
            <v-col cols="2">
              <div>
                <v-avatar color="white" width="50" height="50">
                  <v-img :src="profile"> </v-img>
                </v-avatar>
              </div>
            </v-col>
            <v-col cols="10">
              <SetNombre @nombre="getNombre" />
            </v-col>
          </v-row>
          <div class="mt-3">
            <v-expand-transition>
              <v-alert v-show="dataNombre.nombre != ''" color="#F660FF">
                <span class="font-weight-bold">{{ dataNombre.nombre }} </span>
                <span class="font-weight-bold"
                  >{{ dataNombre.segundoNombre }}
                </span>
                <br />
                <span class="font-weight-bold"
                  >{{ dataNombre.apellidoPaterno }}
                </span>
                <span class="font-weight-bold">{{
                  dataNombre.apellidoMaterno
                }}</span>
              </v-alert>
            </v-expand-transition>
          </div>
          <v-row>
            <v-col cols="2">
              <div>
                <v-avatar color="white" width="50" height="50">
                  <v-img :src="profile"> </v-img>
                </v-avatar>
              </div>
            </v-col>
            <v-col cols="10">
              <SetFechaNacimiento @fecha="getFecha" />
            </v-col>
          </v-row>
          <div class="mt-3">
            <v-expand-transition>
              <v-alert v-show="dataFecha.dia != ''" color="#F660FF">
                <span class="font-weight-bold">{{ dataFecha.dia }} </span>
                <span class="font-weight-bold">{{ dataFecha.mes }} </span>
                <span class="font-weight-bold">{{ dataFecha.año }} </span>
              </v-alert>
            </v-expand-transition>
          </div>
          <v-row>
            <v-col cols="2">
              <div>
                <v-avatar color="white" width="50" height="50">
                  <v-img :src="profile"> </v-img>
                </v-avatar>
              </div>
            </v-col>
            <v-col cols="10">
              <SetDatosContacto @contacto="getContacto" />
            </v-col>
          </v-row>
          <div class="mt-3">
            <v-expand-transition>
              <v-alert v-show="dataContacto.correo != ''" color="#F660FF">
                <span>Correo: </span>
                <span class="font-weight-bold">{{ dataContacto.correo }}</span>
                <br />
                <span>Telefono: </span
                ><span class="font-weight-bold">{{
                  dataContacto.telefono
                }}</span>
              </v-alert>
            </v-expand-transition>
          </div>
          <div class="mt-3">
            <v-expand-transition>
              <v-alert v-show="dataFecha.dia != ''" color="#F660FF">
                Fecha de nacimiento:
                <span class="font-weight-bold">{{ dataFecha.dia }} </span>
                <span class="font-weight-bold">{{ dataFecha.mes }} </span>
                <span class="font-weight-bold">{{ dataFecha.año }} </span>
                <br />
                Correo electronico:
                <span class="font-weight-bold">{{ dataContacto.correo }}</span>
                <br />
                Telefono celular:
                <span class="font-weight-bold">{{
                  dataContacto.telefono
                }}</span>
                <br />
                Nombre:
                <span class="font-weight-bold"
                  >{{ dataNombre.segundoNombre }}
                </span>

                <span class="font-weight-bold"
                  >{{ dataNombre.apellidoPaterno }}
                </span>
                <span class="font-weight-bold">{{
                  dataNombre.apellidoMaterno
                }}</span>
              </v-alert>
            </v-expand-transition>
          </div>
        </v-container>
      </v-sheet>
      <v-container>
        <v-btn @click="enviarDatos" block class="white--text" color="#F660FF">
          Enviar <v-icon right>mdi-send</v-icon>
        </v-btn>
      </v-container>
    </div>
    <v-snackbar
      color="#F660FF"
      :timeout="timeout"
      transition="slide-y-reverse-transition"
      bottom
      right
      v-model="snackbar"
    >
      {{ text }}
      <template v-slot:action="{ attrs }">
        <v-btn color="white" text v-bind="attrs" @click="snackbar = false">
          Cerrar
        </v-btn>
      </template>
    </v-snackbar>
  </v-container>
</template>


<script>
import BarraNavegacion from "@/components/BarraNavegacion";
import SetNombre from "@/components/SetNombre";
import SetFechaNacimiento from "@/components/SetFechaNacimiento";
import SetDatosContacto from "@/components/SetDatosContacto";
export default {
  name: "Chat",

  components: {
    BarraNavegacion,
    SetNombre,
    SetFechaNacimiento,
    SetDatosContacto,
  },
  data() {
    return {
      dataNombre: "",
      dataFecha: "",
      dataContacto: "",
      profile:
        "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcR_nKs_E-HRVBB8pLvZ3QEVUVRPA4P-wpeHWg&usqp=CAU",
      snackbar: false,
      timeout: 4000,
      text: "",
    };
  },
  methods: {
    getNombre($event) {
      this.dataNombre = $event;
      console.log("Nombre", this.dataNombre);
    },
    getFecha($event) {
      this.dataFecha = $event;
      console.log("Fecha", this.dataFecha);
    },
    getContacto($event) {
      this.dataContacto = $event;
      console.log("contacto", this.dataContacto);
    },
    enviarDatos() {
      localStorage.setItem("Nombre", JSON.stringify(this.dataNombre));
      let Nombre = JSON.parse(localStorage.getItem("Nombre"));
      console.log(Nombre);
      localStorage.setItem("Fecha", JSON.stringify(this.dataFecha));
      let Fecha = JSON.parse(localStorage.getItem("Fecha"));
      console.log(Fecha);
      localStorage.setItem("Contacto", JSON.stringify(this.dataContacto));
      let Contacto = JSON.parse(localStorage.getItem("Contacto"));
      console.log(Contacto);
      this.snackbar = true;
      this.text = "Datos enviados correctamente";
    },
  },
};
</script>
