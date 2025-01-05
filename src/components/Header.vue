<template>
    
      
    <!-- Header -->
    <q-header class="header">
      <q-toolbar class = "q-ma-md searchh ">
        <q-input
          outlined
          v-model="text"
          label="Search"
          :dense="dense"
          class="search"
        >
          <template v-slot:append>
            <q-icon name="search" class="q-pa-sm" />
          </template>
        </q-input>

        <!-- <q-space /> -->

        <!-- Text and Avatar -->
        <div class="q-ma-md user-info">
          <span class="q-mr-md user-text">Hello, User</span>
          
          <q-avatar size="40px">
            <img src="https://cdn.quasar.dev/img/boy-avatar.png" alt="User Avatar" />
          </q-avatar>
        </div>

      </q-toolbar>
    </q-header>

    <!-- Main Content -->
    
</template>

<script>
import { ref } from "vue";
// import { shuffle } from "lodash";

export default {
name: "HeaderView",
components: {},

setup() {
return {
  slide: ref("style"),
  lorem: "Lorem ipsum dolor, sit amet consectetur adipi.",
  selection: ref(["green"]),
};
},
};
</script>

<style scoped>




.header {
background-color: #F1F0F5;
}

/* how to change the height of the search element and its width? */


.searchh {
display: flex;            /* Enables Flexbox */
align-items: center;      /* Vertically aligns content */
justify-content: space-between; /* Creates space between search and user info */
     /* Optional: Adds padding on the sides */
}
/* Search Bar Styles */
.search {
flex: 1;                  /* Takes available space */
max-width: 866px;
      /* Restricts maximum width */

    /* Optional: Adds space between search and user info */
}

.user-info {
display: flex;
align-items: center;      /* Vertically aligns text and avatar */
             /* Adds spacing between text and avatar */
}

.label.q-field {
height: 30px !important;
}



.user-text {
color: #464255;
}

/* :deep(.search .q-field__control),
:deep(.search .q-field__marginal) {
height: 40px;
font-size: 16px;
} */

/* .q-field__control {
display: flex;
align-items: center;
height: 40px;
font-size: 30px;
}

.input {
font-size: 16px;
} */

</style>