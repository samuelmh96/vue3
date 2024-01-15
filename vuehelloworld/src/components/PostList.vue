<template>
    <div class="post-detail-container">
        <div>Post Detail</div>
        <div class="container">
            <PostDetail 
                v-for="info in infos" :key="info.id"
                :title="info.title" 
                :content="info.content"
                @sayHi="showAlert"/>
        </div>
    </div>
  
</template>
<script lang="ts" setup>
import PostDetail from './PostDetail.vue';
interface Post {
    id: number,
    title: string,
    content: string
}

let infos:Array<Post> = [
    {
        id: 1,
        title: "This is a test post",
        content: `Lorem ipsum dolor sit amet, consectetur adipiscing el`
    },
    {
        id: 2,
        title: "Another Test Post",
        content: `Ut enim ad minim veniam, quis nostrud exercitation`
    },
    {
        id: 3,
        title: "Exciting Third Post",
        content: `Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.`
    },
    {
        id: 4,
        title: "Yet Another Post",
        content: `Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.`
    },
    {
        id: 5,
        title: "Fifth Post's Charm",
        content: `Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium.`
    }
];

function showAlert(msg: string) {
    alert(msg);
}

</script>

<style scoped>
.post-detail-container {
    text-align: center;
    padding: 20px;
    background-color: #f0f0f0; 
}

.container {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
}

.post-detail {
    width: 200px;
    height: 150px;
    margin: 10px;
    padding: 10px;
    border-radius: 8px;
    background-color: #92c7a3; 
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1); 
    overflow: hidden;
    transition: transform 0.3s ease-in-out;
}

.post-detail:hover {
    transform: scale(1.05); 
}

.post-detail h3 {
    color: #4d7c4c; 
    margin-bottom: 8px;
    transition: color 0.3s ease-in-out; 
}

.post-detail:hover h3 {
    color: #2c5e35; 

.post-detail p {
    color: #333; 
    transition: color 0.3s ease-in-out; 
}

.post-detail:hover p {
    color: #555; 
}

@media (max-width: 768px) {
    .container {
        flex-direction: column; 
        align-items: center;
    }

    .post-detail {
        width: 100%; 
    }
}
</style>