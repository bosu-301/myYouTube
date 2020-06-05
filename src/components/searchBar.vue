<template>
  <nav class="navbar navbar-white bg-white w-100 aligm-item-center ml-5" style="height:56px;">
    <div>

    <button class="navbar-toggler toggler-example" type="button" data-toggle="collapse" data-target="#navberYoutube" aria-controls="navberYoutube" aria-expanded="false" aria-label="Toggle navigation">
      <span class="dark-blue-text"><i class="fas fa-bars fa-1x"></i></span>
    </button>

    <a class="navbar-brand h-100 align-self-start p-0" href="#"><img src="../../public/youtubePremium.png" alt="" style="height:40px;"></a>
    </div>
    <!-- 원래 여기 아래 검색창을 div가 아니라 form 으로 감쌌었는데 그러니까 페이지가 refresh된다. 조심하자 -->
    <div class="col-6 form-inline my-2 my-md-0">
      <input class="form-control w-50" type="search" placeholder="Search" aria-label="Search" v-model="input" @keypress.enter="onInput">
      <button class="btn d-inline" style="width:38px;" @click="onInput"><i class="fas fa-search"></i></button>
    </div>
    <div class="iconBox col-auto text-secondary d-none d-lg-block" >
      <button class="btn d-inline mr-3" style="width:38px;"><i class="fas fa-video"></i></button>
      <button class="btn d-inline mr-3" style="width:38px;"><i class="fas fa-th"></i></button>
      <button class="btn d-inline mr-3" style="width:38px;"><i class="fas fa-bell"></i></button>
    </div>
    <div class="navbar-collapse collapse" id="navberYoutube" style="">
      <ul class="navbar-nav mr-auto">
        <li class="nav-item active">
          <a class="nav-link" href="#">Home <span class="sr-only">(current)</span></a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Link</a>
        </li>
        <li class="nav-item">
          <a class="nav-link disabled" href="#" tabindex="-1" aria-disabled="true">Disabled</a>
        </li>
        <li class="nav-item dropdown">
          <a class="nav-link dropdown-toggle" href="#" id="dropdown01" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">Dropdown</a>
          <div class="dropdown-menu" aria-labelledby="dropdown01">
            <a class="dropdown-item" href="#">Action</a>
            <a class="dropdown-item" href="#">Another action</a>
            <a class="dropdown-item" href="#">Something else here</a>
          </div>
        </li>
      </ul>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'SearchBar',
  data() {
    return {
      input: ''
    }
  },
  methods: {
    onInput() {
      // 위로 이벤트와 값을 쏜다

      this.$emit('input-search', this.input)
      // event.target.value = ''
    }
  },
  beforeMount() {
      window.addEventListener("beforeunload", event => {
        if (!this.isEditing) return
        event.preventDefault()
        // Chrome requires returnValue to be set.
        event.returnValue = ""
      })
    }
}
</script>

<style>
.iconBox i{
  color:rgb(66, 66, 66);
}
</style>