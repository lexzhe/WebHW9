<template>
    <div class="middle">
<!--        <aside>-->
<!--            <SidebarPost v-for="post in viewPosts" :post="post" :users="users" :key="post.id"/>-->
<!--        </aside>-->
        <Sidebar :users="users" :posts="posts"/>
        <main>
            <Index v-if="page === 'Index'"/>
            <Enter v-if="page === 'Enter'"/>
            <Users v-if="page === 'Users'" :users="users"/>
            <Register v-if="page === 'Register'"/>
            <AddPost v-if="page === 'AddPost'"/>
            <EditPost v-if="page === 'EditPost'"/>
        </main>
    </div>
</template>
<script>
    import Index from './middle/Index';
    import Users from './middle/Users';
    import Enter from './middle/Enter';
    import Register from './middle/Register';
    import AddPost from './middle/AddPost';
    // import SidebarPost from './SidebarPost';
    import EditPost from "./middle/EditPost";
    import Sidebar from "./Sidebar";

    export default {
        name: "Middle",
        props: ['users', 'posts'],
        data: function () {
            return {
                page: "Index"
            }
        },
        // computed: {
        //     viewPosts: function () {
        //         return Object.values(this.posts).sort((a, b) => b.id - a.id).slice(0, 2);
        //     }
        // },
        components: {
            EditPost,
            Index,
            Enter,
            Register,
            // SidebarPost,
            AddPost,
            Users,
            Sidebar,
        }, beforeCreate() {
            this.$root.$on("onChangePage", (page) => {
                this.page = page;
                // this.post = post;
            });
        }
    }
</script>

<style scoped>

</style>
