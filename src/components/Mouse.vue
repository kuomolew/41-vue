<!-- 2. Создайте функцию, которая будет на нажатие кнопки мыши предлагать пользователю два варианта: 
 при нажатии на первый – выполняется функция, которая показывает, какая клавиша мыши была нажата; 
 при нажатии на другой – выводится текущее время.-->

 <template >
    <div class="container" @click='showVariants' :class="{awaited: !isShown}">
        <p v-text="text"></p>
        <div class="variant awaited" v-show="isShown" @click.stop='showButton'>1</div>
        <div class="variant awaited" v-show="isShown" @click.stop='showTime'>2</div>
    </div>
</template>
<script>
export default {
    name: "Mouse",
    data() {
        return {
            isShown: false,
            text: 'Press Me'
        }
    },
    methods: {
        showVariants() {
            this.isShown ? this.text = 'Press Me' : this.text = 'Choose variant';
            this.isShown = !this.isShown;
        },
        showButton() {
            this.text = 'Button';
        },
        showTime() {
            this.text = 'Time';
        }
    },
}
</script>
<style>
.container {
    width: 90%;
    margin: 50px auto 50px auto;
    border: 1px solid black;
    background-color: aliceblue;
    display: flex;
    justify-content: space-around;
    flex-wrap: wrap;
    padding: 20px 10px;
}
.container p {
    width: 100%
}
.awaited {
    cursor: pointer;
}
.variant {
    width: 20%;
    padding: 50px 0;
    font-size: 2rem;
    background-color: bisque;
    border: 1px solid black;
}
</style>