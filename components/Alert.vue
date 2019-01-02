<template>
  <div>
    <v-alert
      :value="true"
      :type="type"
    >
      {{ message }}
    </v-alert>
  </div>
</template>

<script>
export default {
  props: ['message', 'type']
}
</script>
