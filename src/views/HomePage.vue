<template>
  <table class="table table-striped table-hover ">
    <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">Başlık</th>
      <th scope="col">URL</th>
      <th scope="col">Sil</th>
    </tr>
    </thead>
    <tbody>
    <tr v-for="i in 10" :key="i">
      <th scope="row">1</th>
      <td>Vue3 Dökümantasyon</td>
      <td>https://v3.vuejs.org</td>
      <td><button class="btn btn-sm btn-danger">Sil</button></td>
    </tr>

    </tbody>
  </table>
</template>