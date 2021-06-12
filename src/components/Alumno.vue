<template>
  <h1>"{{ nombre }}"</h1>
</template>

<script>
export default {
  name: "Alumno",
  props: {
    nombre: String,
  },
};
</script>