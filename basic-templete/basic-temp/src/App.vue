<script setup>
 const accounts = [{
   name: 'salary',
   amount: 10000
  },
  {
   name: 'rent',
   amount: -2500
  },
  {
   name: 'parking fee',
   amount:0
  },
  {name: 'car fuel',
   amount: -600
  },
  {
    name: 'commission',
   amount: 5500
  }]
</script>
 
<template>
  <h2 class="flex justify-center p-8 text-2xl">MY ACCOUNT</h2>
  <div class="md:hidden">
  <ul v-for="account in accounts">
    <li class="p-3 border-solid border-2 border-indigo-500/50 m-2 rounded lg" v-if="account.amount != 0 ">
      <b class="pr-6">Name:</b>  {{account.name}}  <br>
      <b class="pr-3">Amount:</b> 
        <span class="rounded lg" :style="account.amount > 0 ? 'background-color: rgb(5 150 105)' : 'background-color: rgb(244 63 94)'">
          {{account.amount}}
        </span>
    </li>
  </ul>
  <p class="flex justify-end pr-6"><b class="pr-3">Net Total:</b> {{accounts.reduce((total,account) => total + account.amount ,0 )}} </p>
  </div>

  <div class="hidden md:block">
  <table class="w-full my-10">
  <thead class="">
    <tr class="">
      <th>Name</th>
      <th>Amount</th>
    </tr>
  </thead>
  <tbody v-for="(account, index) in accounts " :key="index">
    <tr v-if="account.amount != 0 ">
      <td class="text-center">{{account.name}} </td>
      <td class="text-center">
          <span class="rounded lg" :style="account.amount > 0 ? 'background-color: rgb(5 150 105)' : 'background-color: rgb(244 63 94)'">
          {{account.amount}}
        </span>
      </td>
    </tr>
    </tbody>
  </table>
   <p class="flex justify-center pr-6"><b class="pr-3">Net Total:</b> {{accounts.reduce((total,account) => total + account.amount ,0 )}} </p>
  </div>
</template>
 

<style>

</style>