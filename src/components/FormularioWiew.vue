<script setup>
import { reactive } from 'vue';

const emit = defineEmits(['add']);
const product = reactive({
  name: '',
  email: '',
  password: '',
  confirmPassword: '',
  birthDate: '',
  address: '',
  city: '',
  state: '',
  hobbies: '',
  programmingLanguage: '',
  biography: ''
});

function save() {
  if (
    product.name === '' ||
    product.email === '' ||
    product.password === '' ||
    product.confirmPassword === '' ||
    product.birthDate === '' ||
    product.address === '' ||
    product.city === '' ||
    product.state === '' ||
    product.hobbies === '' ||
    product.programmingLanguage === '' ||
    product.biography === ''
  ) {
    alert('All fields are required');
    return;
  }
  emit('add', { ...product });
}
</script>

<template>
<form @submit.prevent="save">
  <div class="row">
    <label for="name">Name</label>
    <input type="text" v-model="product.name" />
  </div>
  <div class="row">
    <label for="email">Email</label>
    <input type="text" v-model="product.email" />
  </div>
  <div class="row">
    <label for="password">Password</label>
    <input type="text" v-model="product.password" />
  </div>
  <div class="row">
    <label for="confirmPassword">Confirm Password</label>
    <input type="text" v-model="product.confirmPassword" />
  </div>
  <div class="row">
    <label for="birthDate">Date of Birth</label>
    <input type="date" v-model="product.birthDate" />
  </div>
  <div class="row">
    <label for="address">Address</label>
    <input type="text" v-model="product.address" />
  </div>
  <div class="row">
    <label for="city">City</label>
    <input type="text" v-model="product.city" />
  </div>
  <div class="row">
    <label for="state">State</label>
    <select name="state" class="state" v-model="product.state">
      <option value="AC">Acre</option>
      <option value="AL">Alagoas</option>
      <option value="AP">Amapá</option>
      <option value="AM">Amazonas</option>
      <option value="BA">Bahia</option>
      <option value="CE">Ceará</option>
      <option value="DF">Federal District</option>
      <option value="ES">Espírito Santo</option>
      <option value="GO">Goiás</option>
      <option value="MA">Maranhão</option>
      <option value="MT">Mato Grosso</option>
      <option value="MS">Mato Grosso do Sul</option>
      <option value="MG">Minas Gerais</option>
      <option value="PA">Pará</option>
      <option value="PB">Paraíba</option>
      <option value="PR">Paraná</option>
      <option value="PE">Pernambuco</option>
      <option value="PI">Piauí</option>
      <option value="RJ">Rio de Janeiro</option>
      <option value="RN">Rio Grande do Norte</option>
      <option value="RS">Rio Grande do Sul</option>
      <option value="RO">Rondônia</option>
      <option value="RR">Roraima</option>
      <option value="SC">Santa Catarina</option>
      <option value="SP">São Paulo</option>
      <option value="SE">Sergipe</option>
      <option value="TO">Tocantins</option>
    </select>
  </div>
  <div class="row">
    <label for="hobbies">Hobbies</label>
    <input type="text" v-model="product.hobbies" />
  </div>
  <div class="row">
    <label for="programmingLanguage">Programming Language</label>
    <input type="text" v-model="product.programmingLanguage" />
  </div>
  <div class="row">
    <label for="biography">Biography</label>
    <input type="text" v-model="product.biography" />
  </div>
  <button type="submit">Save</button>
</form>
</template>
