<template>
  <div class="input-search">
        <label for="search">
            Pesquise seu vídeo aqui:
            <input id="search" @change="onInput" placeholder="Digite e pressione enter">
        </label>
  </div>
</template>

<script>
export default {
 name: 'SearchVideo',
 methods: {
   onInput: function(event){
      this.$emit('termChange', event.target.value);
   }
 },
};
</script>

<style lang="scss" scoped>

$red: #ff0000;
$black: #282828;

.input-search {
    padding: 30px 0;
    width: 500px;
    max-width: 100%;
    margin: 0 auto;
    label {
        font-size: 22px;
        line-height: 32px;
        color: $black;
        font-weight: bold;
    }
    input {
        width: 100%;
        border: none;
        box-shadow: 0 0 20px rgba(0,0,0,0.2);
        padding: 10px 15px;
        border-radius: 6px;
        font-size: 15px;
        line-height: 22px;
        font-weight: 400;
        color: $black;
        margin-top: 15px;
        box-sizing: border-box;
    }
}
</style>