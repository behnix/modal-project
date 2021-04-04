<template>
    <div class="backdrop" @click.self="closeModal">
        <div class="modal" :class="{ sale: theme === 'sale'}">
            <slot></slot>
            <div class="actions">
                <slot name="link"></slot>
            </div>
        </div>
    </div>
</template>

<script>
    export default{
        props:['theme'],
        methods:{
            closeModal(){
                this.$emit('close');
            }
        }
    }
</script>


<style>
.backdrop{
    background: rgba(0, 0, 0, 0.5);
    position: fixed;
    top: 0;
    width: 100%;
    height: 100%;
}

.modal{
    width: 50%;
    margin: 100px auto;
    border: thin solid black;
    border-radius: 10px;
    background: ghostwhite;
    padding: 20px;

}
.modal h2{
    color: green;
}
.modal.sale{
    background: crimson;
    color: white;
}
.modal.sale h2{
    color: white;
}
.modal .actions{
    text-align: center;
    margin: 30px 0 10px 0;

}
.modal a{
    border: thin solid #ddd;
    padding: 8px;
    color: #ddd;
    border-radius: 4px;
    text-decoration: none;
    margin: 10px;
}
</style>