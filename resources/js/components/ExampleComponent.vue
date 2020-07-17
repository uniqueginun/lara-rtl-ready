<template>
    <div class="container">
        name: {{ user.name }} <br />
        email: {{ user.email }} <br />
    </div>
</template>

<script>
    export default {

        data: function () {
            return {
                user: {}
            }
        },

        methods: {
          async getCurrentAuthenticatedUser () {
                const { data } = await axios.get('/api/user')
                this.user = data
            }
        },

        mounted() {
            this.getCurrentAuthenticatedUser()
        }
    }
</script>
