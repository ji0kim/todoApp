
<template>
  <div class="input-box shadow">
        <input type="text" v-model="newTodoItem" v-on:keyup.enter="addTodo">
        <span class="add-container" v-on:click="addTodo"><i class="fas fa-plus add-btn"></i></span>
        <Modal v-if="showModal" @close="showModal = false">
            <h3 slot="header">
                앗!
                <i class="fas fa-times closeModalBtn" @click="showModal = false"></i>
            </h3>
            <p slot="body">할 일을 입력해주세요.</p>
        </Modal>
  </div>

</template> 

<script>
import Modal from './common/Modal.vue'
export default {
    data: function(){
      console.log('djdj');
        return {
            newTodoItem: "",
            showModal: false

        }


    },
    methods: {
        addTodo (){
            if (this.newTodoItem !== ''){
                this.$emit('addTodoItem', this.newTodoItem);
                this.clearInput();
            } else {
               this.showModal = !this.showModal; 
            }
        },
        clearInput(){
            this.newTodoItem = ''; 
        }
    },
    components: {
        Modal
    }
}
</script>

<style >
.input-box {background: white; height: 50px; line-height: 50px; border-radius: 5px;}
.input-box input {border-style: none; font-size: 0.9rem; width: calc(100% - 80px); line-height: 48px;}
.add-container {float: right; background: linear-gradient(to right, #6478FB, #8763FB); display: block; width: 3rem; border-radius: 0 5px 5px 0;}
.add-btn {color: #fff; vertical-align: middle;}
.closeModalBtn {color: #42b983;}
</style>