<template>
    <div>
        <form>
            <br><br>
            <div class="input">
                <input type="text" id="new" class="form-control" placeholder="New Todo" v-model="newList">
            </div>
            
            <button class="btn btn-primary" @click.prevent="createNew" hidden>New Todo</button>

             <!-- <div class="alert alert-danger">Click list to delete</div> -->
        </form>
        
        <hr>
    </div>
</template>

<script>
    export default {
      data() {
          return {
              newList: ''
          }
      },
      methods: {
          createNew() {
              this.$emit('emitList', this.newList)
              this.newList = '' // to reset form after sending data
          },
      },
    }
</script>

<style scoped>
    .form-control {
        width: 50%;
    }

    .input {
        display: flex;
        justify-content: center;
    }
</style>