<template>
    <div class="app">
        <post-form @create="createPost"/>
        <post-list :posts="posts" />
        
    </div>
</template>

<script>
import PostForm from "@/components/PostForm.vue"
import PostList from "@/components/PostList.vue";

export default {
    components: {
        PostList, PostForm
    },
    data() {
        return {
            posts: [
                {id: 1, title: 'JavaScript', body: 'Описание поста'},
                {id: 2, title: 'JavaScript2', body: 'Описание поста 2'},
                {id: 3, title: 'JavaScript3', body: 'Описание поста 3'},
                {id: 4, title: 'JavaScript4', body: 'Описание поста 4'},
            ],
        }
    },
    methods: {
        createPost(post) {
            console.log(post);
            this.posts.push(post);

            // if (this.title == '' || this.body == '')
            // return;

            // const newPost = {
            //     id: Date.now,
            //     title: this.title,
            //     body: this.body,
            // }
            // this.posts.push(newPost);
            // this.title = '';
            // this.body = '';
        },
        inputTitle(event) {
            this.title = event.target.value;
        }
    }
}

</script>

<style>
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

.app {
    padding: 20px;
}


</style>