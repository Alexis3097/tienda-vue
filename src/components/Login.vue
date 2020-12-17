<template>
  <v-app>
    <v-content>
      <v-container class="fill-height" fluid>
        <v-row align="center" justify="center">
          <v-col cols="12" sm="8" md="8">
            <v-card class="elevation-12">
              <v-window v-model="step">
                <v-window-item :value="1">
                  <v-row>
                    <v-col cols="12" md="8">
                      <v-card-text class="mt-12">
                        <h1 class="text-center display-2 teal--text text--accent-3">
                          Iniciar Sesión
                        </h1>
                        <div class="text-center mt-4">
                            <v-btn class="mx-2" fab color="black" outlined>
                                <v-icon>fab fa-facebook-f</v-icon>
                            </v-btn>
                             <v-btn class="mx-2" fab color="black" outlined>
                                <v-icon>fab fa-linkedin-in</v-icon>
                            </v-btn>
                               <v-btn class="mx-2" fab color="black" outlined>
                                <v-icon>fab fa-github</v-icon>
                            </v-btn>
                        </div>
                        <h4 class="text-center mt-4">Ingresa tu Email para iniciar Sesion.</h4>
                        <v-form v-model="valid">
                            <v-text-field
                            v-model="email"
                            :rules="emailReglas"
                            label="Email"
                            name="Email"
                            prepend-icon="email"
                            type="text"
                            color="teal accent-3"
                            required
                            />
                            <v-text-field  
                            v-model="password"
                            :rules="passwordReglas"                          
                            id="password"
                            label="Password"
                            name="Password"
                            prepend-icon="lock"
                            type="password"
                            color="teal accent-3"
                            required
                            />
                        </v-form>
                        <h3 class="text-center mt-3">¿Olvidaste tu contraseña?</h3>
                      </v-card-text>
                        <div class="text-center mt-3">
                            <v-btn rounded color="teal accent-3" dark @click="Login">Iniciar Sesión</v-btn>
                        </div>
                    </v-col>
                    <v-col cols="12" md="4" class="teal accent-3">
                        <v-card-text class="white--text mt-12">
                            <h1 class="text-center display-1 mb-2">Aun no estas registrado!</h1>
                            <h5 class="text-center">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Eaque dicta animi nisi quisquam?</h5>
                        </v-card-text>
                        <div class="text-center mt-4">
                            <v-btn rounded outlined="" dark @click="step++">Registrate</v-btn>
                        </div>
                    </v-col>
                  </v-row>
                </v-window-item>
                <v-window-item :value="2">
                    <v-row class="fill-height">
                        <v-col cols="12" md="4" class="teal accent-3">
                            <v-card-text class="white--text mt-12">
                                <h1 class="text-center display-1 mb-2">Regresar a Inicio de Sesión!</h1>
                                <h5 class="text-center">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Eaque dicta animi nisi quisquam?</h5>
                            </v-card-text>
                            <div class="text-center mt-4">
                                <v-btn rounded outlined="" dark @click="step--">Iniciar Sesión</v-btn>
                            </div>
                        </v-col>
                        <v-col cols="12" md="8">
                            <v-card-text class="mt-12">
                            <h1 class="text-center display-2 teal--text text--accent-3">Crear una cuenta.</h1>
                        <div class="text-center mt-4">
                            <v-btn class="mx-2" fab color="black" outlined>
                                <v-icon>fab fa-facebook-f</v-icon>
                            </v-btn>
                             <v-btn class="mx-2" fab color="black" outlined>
                                <v-icon>fab fa-linkedin-in</v-icon>
                            </v-btn>
                               <v-btn class="mx-2" fab color="black" outlined>
                                <v-icon>fab fa-github</v-icon>
                            </v-btn>
                        </div>
                        <h4 class="text-center mt-4">Registra una nueva cuenta.</h4>
                        <v-form>
                            <v-text-field
                            label="Nombre"
                            name="Nombre"
                            prepend-icon="person"
                            type="text"
                            color="teal accent-3"
                            />
                            <v-text-field
                            label="Email"
                            name="Email"
                            prepend-icon="email"
                            type="text"
                            color="teal accent-3"
                            />
                            <v-text-field
                            id="password"
                            label="Password"
                            name="Password"
                            prepend-icon="lock"
                            type="password"
                            color="teal accent-3"
                            />
                        </v-form>                        
                      </v-card-text>
                        <div class="text-center mt-3">
                            <v-btn rounded color="teal accent-3" dark>Registrar</v-btn>
                        </div>
                        </v-col>              
                    </v-row>
                </v-window-item>
              </v-window>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
export default {
  data: () => ({
      step: 1,
      valid: false,     
      nombre: '',
      nombreReglas: [
        v => !!v || 'El campo nombre es requerido'
        // v => v.length <= 10 || 'Name must be less than 10 characters',
      ],
      email: '',
      emailReglas: [
        v => !!v || 'El campo Email es requerido',
        v => /.+@.+/.test(v) || 'Igrese un Email valido',
      ],
      password:'',
      passwordReglas:[
          v=>!!v || 'La constraseña es requerido',          
      ],
    }),
    
    methods:{
        Login(){
            return alert("aqui la logica del inicio de sesion");            
        }
    }
};
</script>