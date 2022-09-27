<template>
    <div class="card-album">
      <img class="w-100" :src="info.poster" :alt="info.title" @error="replaceWrongImageUrl" />
      <p> {{ info.title }}</p>
    </div>
  </template>
  
  <script>
  
  import errorImage from '@/assets/img/logo.png'
  
  export default {
      name: 'AlbumCardComponent',
      props:{
          info: Object
      },
      methods:{
          replaceWrongImageUrl(e){
              console.log('errore');
            e.target.src = errorImage
          }
      }
  }
  </script>
  
  <style lang="scss" scoped>
  .card-album{
      display: flex;
      flex-direction: column;
      padding: 10px;
      background-color: #2e3a46;
      color: #ccc;
      text-align: center;
      height: 100%;
      p{
          color: #fff;
          text-transform: uppercase;
          margin-top: 5px;
      }
  }
  </style>