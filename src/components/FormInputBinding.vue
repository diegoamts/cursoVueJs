<script setup>
import { ref } from 'vue';
const text = ref("Olá")
const message = ref('')

const checked = ref(false)
const checkedNames = ref([])

const picked = ref()

const selected = ref('A')

const options = ref([
    { text: 'One', value: 'A' },
    { text: 'Two', value: 'B' },
    { text: 'Three', value: 'C' }
])

const first = ref('primeiro')
const second = ref('segundo')
const pick = ref('')


</script>
<template>
    <input type="text" :value="text" @input="event => text = event.target.value">
    <input type="text" v-model="text">
    <p>Message is: {{ message }}</p>
    <input type="text" v-model="message" placeholder="Edit me...">

    <span>
        Multiline message is:
    </span>
    <p style="white-space: pre-line;">
        {{ message }}
    </p>
    <textarea v-model="message" name="" id="" cols="30" rows="10"></textarea>

    <input type="checkbox" id="checkbox" v-model="checked" />
    <label for="checkbox">{{ checked }}</label>

    <div>
        Checked names: {{ checkedNames }}
    </div>
    <input type="checkbox" name="jack" id="jack" value="Jack" v-model="checkedNames">
    <label for="jack">Jack</label>

    <input type="checkbox" name="john" id="john" value="John" v-model="checkedNames">
    <label for="john">John</label>

    <input type="checkbox" name="mike" id="mike" value="Mike" v-model="checkedNames">
    <label for="mike">Mike</label>

    <div>
        Picked: {{ picked }}
    </div>
    <input type="radio" id="one" value="One" v-model="picked">
    <label for="one">One</label>

    <input type="radio" id="two" value="Two" v-model="picked">
    <label for="two">Two</label>


    <div>
        Selected : {{ selected }}
    </div>
    <select v-model="selected">
        <option value="" disabled>Please select one</option>
        <option>A</option>
        <option>B</option>
        <option>C</option>
    </select>

    <div>
        Selected: {{ selected }}
    </div>

    <select v-model="selected" multiple>
        <option>A</option>
        <option>B</option>
        <option>C</option>
    </select>

    <select v-model="selected">
        <option v-for="option in options" :value="option.value">
            {{ option.text }}
        </option>
    </select>

    <div>Selected: {{ selected }}</div>

    <input type="radio" v-model="pick" :value="first" />
    <input type="radio" v-model="pick" :value="second" />

    <div>
        Picked: {{ pick }}
    </div>

    <input type="number" v-model.number="age">
    <input v-model.trim="msg">

</template>