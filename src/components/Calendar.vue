<template>

    <q-page-container>
        <q-page class="q-pa-md">
          <h1 class="text-h4">Welcome to My App</h1>
          <p>This is the main body content of the app. Customize it as needed.</p>
          <q-btn label="Click Me" color="primary" @click="onButtonClick" />
        </q-page>
    </q-page-container>
</template>

<script>
export default {
  name: 'PageCalendar'
}
</script>