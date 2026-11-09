<script>
  export default{
    data(){
      return {
        posts: [
          {id:1, title: "meow", body:"description"},
          {id:2, title: "meow", body:"description"},
          {id:3, title: "meow", body:"description"},
          {id:4, title: "meow", body:"description"},
          {id:5, title: "meow", body:"description"}
        ],
        title:'',
        body:''
      }
    },
    methods: {
      createPost(){
        const newPost = {
          id: Date.now(),
          title: this.title,
          body: this.body,
        }
        this.posts.push(newPost)
      }
    }
  }
</script>

<template>
  <div v-for="post in posts">
    <p>{{post.title}}</p>
    <p>{{post.body}}</p>
  </div>
  <div>
    <input v-bind:value="title" @input="title = $event.target.value" type="text" placeholder="title">
    <input v-bind:value="body" @input="body = $event.target.value" type="text" placeholder="body"/>
    <button @click="createPost">Добавить</button>
  </div>
</template>
