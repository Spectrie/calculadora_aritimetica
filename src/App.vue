<script setup>
  import {reactive} from 'vue';
  import Display from './components/Display.vue'
  import Buttons from './components/Buttons.vue'

  const estado = reactive ({
    display: '',//exibe os numeros e operaçoes
  })

  const appendToDisplay = (value) => { 
    estado.display += value;
  }

  const clear = () => {
    estado.display = '';
  }

  const deleteLast = () => {
    estado.display = estado.display.slice(0, -1);
  }

  const calculate = () => {
    try{
      estado.display = eval(estado.display).toString();
    }catch(error){
      estado.display = 'Erro'
    }
  }
</script>

<template>
    <Display :displayValue="estado.display"/>
<div class="container">
    <div class="row mb-4">
    <div class="col-sm-3">
      <Buttons value="7" :onClick="appendToDisplay" />
    </div>
    <div class="col-sm-3">
      <Buttons value="8" :onClick="appendToDisplay" />
    </div>
    <div class="col-sm-3">
      <Buttons value="9" :onClick="appendToDisplay" />
    </div>
    <div class="col-sm-3">
      <Buttons value="+" id="operation"  :onClick="appendToDisplay" />
    </div>
    </div>
    <div class="row mb-4">
    <div class="col-sm-3">
        <Buttons value="4" :onClick="appendToDisplay" />
    </div>
    <div class="col-sm-3">
    
      <Buttons value="5" :onClick="appendToDisplay" />
    </div>
    <div class="col-sm-3">
      <Buttons value="6" :onClick="appendToDisplay" />
    </div>
    <div class="col-sm-3">
      <Buttons value="-" id="operation" :onClick="appendToDisplay" />
    </div>
    </div>
<div class="row mb-4">
    <div class="col-sm-3">
      <Buttons value="1" :onClick="appendToDisplay" />
    </div>
    <div class="col-sm-3">
      <Buttons value="2" :onClick="appendToDisplay" />
    </div>
    <div class="col-sm-3">
      <Buttons value="3" :onClick="appendToDisplay" />
    </div>
    <div class="col-sm-3">
      <Buttons value="*" id="operation" :onClick="appendToDisplay" />
    </div>
</div>
<div class="row mb-4">
    <div class="col-sm-3">
      <Buttons value="." id="operation" :onClick="appendToDisplay" />
    </div>
    <div class="col-sm-3">
      <Buttons value="0" :onClick="appendToDisplay" />
    </div>
    <div class="col-sm-3">
      <Buttons value="%" id="operation" :onClick="appendToDisplay" />
    </div>
    <div class="col-sm-3">
      <Buttons value="/" id="operation" :onClick="appendToDisplay" />
    </div>
</div>
<div class="row mb-4">
    <div class="col-sm-3">
      <Buttons value="CE" id="operation" :onClick="clear" />
    </div>
    <div class="col-sm-3">
      <Buttons value="C" id="operation" :onClick="deleteLast" />
    </div>
    <div class="col-sm-3 ms-auto">
      <Buttons value="=" id="operation" :onClick="calculate" />
    </div>
    </div>
</div>
</template>

<style scoped>
</style>
