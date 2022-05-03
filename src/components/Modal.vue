<template>
    <div class="backdrop" @click="closeModal"> 
        <div class="modal">
            <h2>
                {{header}}
            </h2>
            <p>I am Iyanu, Learning Vue {{title}}</p>
        </div>
    </div>
</template>


<script>
export default {
    props:['header', 'title'],
    methods: {
        closeModal(){
            this.$emit('close')
        }
    }

}
</script>

<style scoped>
.modal{
    width: 400px;
    padding: 20px;
    margin: 100px auto;
    background: #000;
    border-radius: 10px;
    z-index: 1000;
}


.backdrop{
    top: 0;
    position: fixed;
    background: rgba(0, 0, 0, 0.5);
    width: 100%;
    height: 100%;
}

h2{
    color:#111;
    font-size:30px;
}

</style>