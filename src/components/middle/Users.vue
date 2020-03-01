<template>
    <section>
        <div class="datatable">
            <table>
                <thead>
                <tr>
                    <th>Id</th>
                    <th>Login</th>
                    <th>Name</th>
                </tr>
                </thead>
                <tbody>
                <tr v-for="u in users" v-bind:key="u.id">
                    <td>{{u.id}}</td>
                    <td>{{u.login}}</td>
                    <td>{{u.name}}</td>
                </tr>
                </tbody>
            </table>
        </div>
    </section>
</template>


<script>
    export default {
        props: ['users'],
        name: "Users",
    }

</script>