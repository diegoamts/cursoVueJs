<script setup>
import { reactive } from 'vue';
import { ref } from 'vue';
import ClassAndStyleBindings from './components/ClassAndStyleBindings.vue';
import ComputedProperties from './components/ComputedProperties.vue';
import TemplateSyntax from './components/TemplateSyntax.vue';

const count = ref(10)
const objRef = ref({count:0})


const state = reactive({
  count: 0
})

function increment(){
  state.count++;
}

const obj = reactive({
  nested:{
    count:0
  },
  arr:[
    'foo',
    'bar'
  ]
})


let obj2 = {
  foo: ref(1),
  bar: ref(2)
}


console.log(obj2.foo)

let {foo, bar} = obj2

function incrementFoo(){
  obj2.foo++
}


function mutateDeeply(){
  obj.nested.count++;
  obj.arr.push('baz')
}

</script>

<template>
  <div>
    <h1>
      Hello World!
    </h1>
  </div>
  <div>
    {{ state.count }}
  </div>
  <div>
    <button @click="increment">
      {{ state.count }}
    </button>
    <button @click="mutateDeeply">
      Count: {{ obj.nested.count }} - Arr: {{ obj.arr.length }}
    </button>
  </div>

  <div>
    <button>
      {{ count }} - {{ objRef.count }}
    </button>
    
  </div>

  <div>
    <button @click="incrementFoo">
      obj2.foo: {{ obj2.foo }}
      foo: {{ foo }}
    </button>
  </div>
  <ComputedProperties></ComputedProperties>
  <TemplateSyntax></TemplateSyntax>
  <ClassAndStyleBindings></ClassAndStyleBindings>
</template>

<style scoped></style>
