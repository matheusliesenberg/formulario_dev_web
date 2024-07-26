<script setup>
defineProps(['products']);
</script>

<template>
<table>
  <tbody>
    <tr v-for="product in products" :key="product.id">
      <td>Name: {{ product.name }}</td>
      <td>Email: {{ product.email }}</td>
      <td>Password: {{ product.password }}</td>
      <td>Confirm Password: {{ product.confirmPassword }}</td>
      <td>Date: {{ product.birthDate }}</td>
      <td>Address: {{ product.address }}</td>
      <td>City: {{ product.city }}</td>
      <td>State: {{ product.state }}</td>
      <td>Hobbies: {{ product.hobbies }}</td>
      <td>Programming Language: {{ product.programmingLanguage }}</td>
      <td>Biography: {{ product.biography }}</td>
    </tr>
  </tbody>
</table>
</template>

