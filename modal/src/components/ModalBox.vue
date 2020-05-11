<template>
  <transition name="modal">
    <div class="modal-mask">
        <div class="modal-wrapper">
            <div class="modal-container">
                <div class="modal-default-button" @click="close">x</div>

                <div class="modal-header">
                    <slot name="header">
                        Default header
                    </slot>
                </div>
                <hr>
                <div class="modal-body">
                    <slot name="body">
                        Default body
                    </slot>
                </div>

                <div class="modal-footer">
                    <slot name="footer">
                        Default footer

                    </slot>
                </div>

            </div>
        </div>
    </div>
  </transition>
</template>

<script>
export default {
    methods:{
        close() {
            this.$emit("close")
        }
    }
}
</script>

<style scoped>
.modal-mask{
  position: fixed;
  z-index: 9998;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  transition: opacity 0.3s ease;
}

.modal-wrapper{
    height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
}

.modal-container{
  min-width: 300px;
  margin: 0px auto;
  padding: 20px 30px;
  background-color: #fff;
  border-radius: 2px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.33);
  transition: all 0.3s ease;
  font-family: Helvetica, Arial, sans-serif;
}

.modal-header{
    margin-top: 0;
    margin-bottom: 10px;
}

.modal-body{
    margin: 20px 0;
}

.modal-default-button{
    float: right;
    width: 1em;
    height: 1em;
    text-align: center;
    cursor: pointer;
    border: black solid 1px;
    border-radius: 10px;
}
</style>
