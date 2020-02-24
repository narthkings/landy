<template>
  <section class>
    <v-row ma-auto wrap>
      <v-col cols="12" lg="6">
        <div class="resizing display-4 font-weight-medium">Learn Japanese</div>
        <div
          class="subtitle-2 text-down"
          style="max-width:25rem "
        >Lorem ipsum dolor sit amet consectetur adipisicing elit. Amet, nesciunt molestiae ex inventore quibusdam id architecto quos cupiditate nobis magnam eum voluptatem quas quis obcaecati dolor vero veritatis similique alias.</div>
        <v-btn style="margin-top:3rem" color="success">Get started</v-btn>
      </v-col>
      <v-col cols="12" lg="6">
        <v-img
          src="/img/undraw_book_lover_mkck.png"
          lazy-src="/img/undraw_book_lover_mkck.png"
          aspect-ratio="1"
          class="justify-center"
          max-width="500"
          max-height="400"
          contain
        ></v-img>
      </v-col>
    </v-row>
    <v-container>
      <v-row wrap class="mt-5">
        <v-col cols="12" md="6" lg="4">
          <div class="d-flex justify-center">
            <v-avatar color="indigo ">
              <v-icon dark>mdi-book-open-page-variant</v-icon>
            </v-avatar>
          </div>

          <div
            class="mt-4 body-1"
          >Lorem ipsum dolor sit amet consectetur adipisicing elit. Quia nisi, veritatis amet ut minima molest modi! Fugiat quos molestias eaque, architecto tenetur ratione</div>
        </v-col>

        <v-col cols="12" md="6" lg="4">
          <div class="d-flex justify-center">
            <v-avatar color="indigo ">
              <v-icon dark>mdi-youtube-subscription</v-icon>
            </v-avatar>
          </div>

          <div
            class="mt-4 body-1"
          >Lorem ipsum dolor sit amet consectetur adipisicing elit. Quia nisi, veritatis amet ut minima molest modi! Fugiat quos molestias eaque, architecto tenetur ratione</div>
        </v-col>

        <v-col cols="12" md="6" lg="4">
          <div class="d-flex justify-center align-content-center">
            <v-avatar color="indigo ">
              <v-icon dark>mdi-headphones</v-icon>
            </v-avatar>
          </div>

          <div
            class="mt-4 body-1"
          >Lorem ipsum dolor sit amet consectetur adipisicing elit. Quia nisi, veritatis amet ut minima molest modi! Fugiat quos molestias eaque, architecto tenetur ratione</div>
        </v-col>
      </v-row>
    </v-container>
    <v-container class="white--text mt-5" grid-list-xs>
      <v-row wrap>
        <v-col cols="12" lg="6">
          <div class="title">
            Reach out to us
            <div>
              <v-form ref="form" v-model="valid" lazy-validation>
                <v-text-field v-model="name" :counter="10" :rules="nameRules" label="Name" required></v-text-field>

                <v-text-field v-model="email" :rules="emailRules" label="E-mail" required></v-text-field>

                <v-textarea rows="1" prepend-icon="mdi-comment"></v-textarea>
              </v-form>
            </div>
          </div>
        </v-col>
        <v-col cols="12" lg="6">
          <div class="title">Address</div>
          <div
            class="body-1"
          >Lorem ipsum dolor sit amet consectetur adipisicing elit. Molestias laudantium blanditiis adipisci minima possimus facilis quae illum. Commodi eum</div>
        </v-col>
      </v-row>
    </v-container>
  </section>
</template>
<script>
export default {
  name: 'landingPage',
  data() {
    return {
      valid: true,
      name: '',
      nameRules: [
        v => !!v || 'Name is required',
        v => (v && v.length <= 10) || 'Name must be less than 10 characters'
      ],
      email: '',
      emailRules: [
        v => !!v || 'E-mail is required',
        v => /.+@.+\..+/.test(v) || 'E-mail must be valid'
      ]
    }
  }
}
</script>
<style >
.text-down {
  margin-top: 1.5rem;
}
@media screen and (max-width: 320px) {
  .text-down {
    margin-top: 0.1rem;
  }
}

@media screen and (max-width: 600px) {
  .text-down {
    margin-top: 0.3rem;
  }
}
@media screen and (max-width: 960px) {
  .text-down {
    max-width: 42rem !important;
    /* margin-top: 0.3rem; */
  }
}

@media screen and (max-width: 600px) {
  .v-application .resizing {
    font-size: 2.9rem !important;
    font-weight: 600 !important;
  }
}
@media screen and (max-width: 320px) {
  .v-application .resizing {
    font-size: 2.4rem !important;
  }
}
.text {
  text-decoration: none;
}
</style>