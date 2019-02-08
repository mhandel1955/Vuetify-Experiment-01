<template>
  <div>
    <v-app>
      <v-content>
        <v-form v-model="valid">
          <v-container>
            <v-layout>
              <v-flex md12 lg4>
                <v-text-field
                  v-model="firstname"
                  :rules="nameRules"
                  :counter="10"
                  label="First name"
                  required
                ></v-text-field>
              </v-flex>

              <v-flex md12 lg4>
                <v-text-field
                  v-model="lastname"
                  :rules="nameRules"
                  :counter="10"
                  label="Last name"
                  required
                ></v-text-field>
              </v-flex>

              <v-flex md12 lg4>
                <v-text-field
                  v-model="email"
                  :rules="emailRules"
                  label="E-mail"
                  required
                ></v-text-field>
              </v-flex>
            </v-layout>
          </v-container>
        </v-form>
      </v-content>
    </v-app>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      valid: false,
      firstname: "",
      lastname: "",
      nameRules: [
        v => !!v || "Name is required",
        v => v.length <= 10 || "Name must be less than 10 characters"
      ],
      email: "",
      emailRules: [
        v => !!v || "E-mail is required",
        v => /.+@.+/.test(v) || "E-mail must be valid"
      ]
    };
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
