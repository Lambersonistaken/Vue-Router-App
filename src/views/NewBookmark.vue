<template>
  <div class="form-area card border p-2">
    <div class="mb-3">
      <label for="title" class="form-label">Başlık</label>
      <input type="text" class="form-control" v-model="userData.title" id="title" placeholder="Başlık Giriniz">
    </div>
    <div class="mb-3">
      <label for="url" class="form-label">URL</label>
      <input type="text" class="form-control" v-model="userData.url" id="url" placeholder="URL Giriniz">
    </div>
    <div class="mb-3">
      <label for="intro" class="form-label">Açıklama</label>
      <textarea class="form-control" id="intro" rows="3" v-model="userData.intro" placeholder="Açıklama Giriniz"></textarea>
    </div>


      <button class="btn btn-sm btn-primary" @click="onSave">Kaydet</button>
      <button class="btn btn-sm btn-secondary mt-2" @click="$router.push({name:'HomePage'})">İptal</button>


  </div>
</template>

<script>

export default  {
  data() {
    return {
      userData: {
        title: null,
        url: null,
        intro:null
      }
    }
  },

  methods: {
    onSave() {
        console.log(this.userData)
        this.$appAxios.post("/bookmarks",this.userData).then(save_response => {
          console.log("save_response",save_response)
          this.resetData()
        })
    },

    resetData() {
      Object.keys(this.userData).forEach(key => (this.userData[key] = null))
    }
  }

}

</script>