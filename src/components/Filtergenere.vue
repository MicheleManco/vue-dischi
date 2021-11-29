<template>
<div>
    <!-- @change="sceltagenere($event)" -->
   <select name="" id="" @change="$emit('search', $event)">
        <option :value="'all'">All</option>
        <option :value="'rock'">Rock</option>
        <option :value="'pop'">Pop</option>
        <option :value="'jazz'">Jazz</option>
        <option :value="'metal'">Metal</option>
   </select>
</div>
  
</template>

<script>

export default {
  name: 'Filtergenere',
}
</script>

<style scoped lang="scss">

</style>