<template>
  <nav class="navbar navbar-white bg-white w-100 aligm-item-center" style="height:56px;">
    <button class="navbar-toggler toggler-example" type="button" data-toggle="collapse" data-target="#navberYoutube" aria-controls="navberYoutube" aria-expanded="false" aria-label="Toggle navigation">
      <span class="dark-blue-text"><i class="fas fa-bars fa-1x"></i></span>
    </button>

    <a class="navbar-brand h-100 align-self-start p-0" href="#"><img src="../../public/youtubePremium.png" alt="" style="height:40px;"></a>
    <form class="col form-inline my-2 my-md-0 align-self-start">
      <input class="form-control w-50" type="search" placeholder="Search" aria-label="Search" @keypress.enter="onInput">
      <button class="btn d-inline" style="width:38px;" @click="onInput"><i class="fas fa-search"></i></button>
    </form>

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
  methods: {
    onInput(event) {
      // 위로 이벤트와 값을 쏜다

      this.$emit('input-search', event.target.value)
      // event.target.value = ''
    }
  }
}
</script>

<style>

</style>