<!--  1. Создайте страницу с текстовым полем ввода. 
При нажатии на кнопку подтверждения, данные из поля должны отображаться в документе, 
поле ввода – очищаться, а фоновый цвет меняться в зависимости от введённого значения.-->


<template >
    <form v-bind:style="{ backgroundColor: setColor }"> 
      <input type="text" v-model="color" placeholder="Type a color:" >
      <button @click.prevent="submitColor">Submit</button>
      <p v-text="setColor"></p> 
    </form>
</template>

<script>
export default {
    name: "Color",
    data() {
        return {
            color: '',
            setColor: ''
        }
    },
    methods: {
        submitColor() {
            this.setColor = this.color;
            this.color = ''
        }
    }
}
</script>

<style>
form {
    padding-top: 60px;
    padding-bottom: 200px;
}
button {
  display: block;
  margin: 0 auto;
  margin-top: 20px;
}
</style>