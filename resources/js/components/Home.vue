<template>
    <v-card>
        <v-card-title style="background-color:#B2DFDB">Home</v-card-title>
        <v-card-text>
            <p>HOME</p>
            <p>some transcations & logics here....</p>
        </v-card-text>
    </v-card>
</template>

<script>
export default {
    data: () => ({

    }),

    mounted(){
        // Authenticate user and retrieve access token
        axios.post('oauth/token', {
            grant_type: 'password',
            client_id: '2',
            client_secret: 'oyrFOeYa4OpNTYF3TEzHMDI9f1HJRM6gJp7zamRS',
            username: 'karl@angelo.com',
            password: 'password',
        })
        .then(response => {
            console.log(response.data)
            // Save the access token in local storage or session
            // const accessToken = response.data.access_token;
            // localStorage.setItem('access_token', accessToken);

            // Set the authorization header for subsequent API requests
            // axios.defaults.headers.common['Authorization'] = `Bearer ${accessToken}`;

            // Redirect the user to the authenticated section of your SPA
        })
        .catch(error => {
            // Handle authentication error
        });


    }
}
</script>