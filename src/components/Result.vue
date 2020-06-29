<template>
  <div>
      <h1>
          Результат
      </h1>
      <h2>
          {{Math.round(mark)}}
      </h2>
  </div>
</template>

<script>
export default {
    props:["mark"]
}
</script>

<style>

</style>