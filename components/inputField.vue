<template>
   <div class="input-row">
      <label class="switch" v-show="showLabel" :for="id">
         {{ label }}
      </label>
      
      <input 
         :id="id"
         :type="type"
         :class="[{'input-error': hasError, 'active': isActive }, fieldSize, 'form-input']"
         :placeholder="placeholder"
         @focus="setActive"
         @blur="validate"
         @input="handleChange"
         v-model="content"
         ref="input"
         autocomplete="off"
      />
   </div>
</template>

<script>
export default {
   name: 'input-field',
   props: {
      label: {
         type: String
      },
      showLabel: {
         type: Boolean,
         default: true
      },
      id: {
         type: String,
         required: true
      },
      type: {
         type: String,
         required: true
      },
      fieldSize: {
         type: String,
         required: false,
         default: "large"
      },
      value: {
         type: String
      },
      placeholder: {
         type: String,
         required: false
      }
   },
   data(){
      return{
         content: this.value,
         hasError: false,
         isActive: false
      }
   },
   methods: {
      validate(){
         this.hasError = (isNaN(this.value) || this.value === '');
         this.isActive = false;
      },
      setActive(){
         this.isActive = true;
      },
      handleChange(e){
         this.$emit('input', this.content);
      }
   }
}
</script>

