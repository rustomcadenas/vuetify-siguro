<template>
    <v-app>
        <div class="d-flex align-center justify-center" style="height: 90vh">
            <v-sheet width="400" class="mx-auto">
                <v-form fast-fail @submit.prevent="Login_F">
                    <v-text-field  variant="underlined" v-model="user_username" label="User Name" :error="error_message != ''" required></v-text-field>

                    <v-text-field variant="underlined" v-model="user_userpass" label="password" :error="error_message != ''" required></v-text-field> 

                    <v-btn :loading="login_loading" type="submit" variant="outlined" color="blue" block class="mt-2">Sign in
                        <template v-slot:loader>
                            <v-progress-linear indeterminate></v-progress-linear>
                        </template>
                    </v-btn> 
                </v-form> 

                <div class="mt-10">
                    <p class="text-body-2 text-red" > {{ error_message }} </p>
                </div>
                <div class="mt-10">
                    <p class="text-body-2 text-red" > {{ msg }} </p>
                </div>
            </v-sheet> 
        </div>
    </v-app>
</template>

<script> 
import axios from '../axios'

export default{
    data(){
        return{
            user_username: "",
            user_userpass: "", 
            error_message: "",
            msg: "",
            login_loading: false,
            result:  ""
        }
    },
    methods:{
        async Login_F(){
            this.msg = "";
            this.login_loading = true;
            let form_data = new FormData();
            form_data.append('user_username', this.user_username)
            form_data.append('user_userpass', this.user_userpass)

            this.result = await axios.post('/loginaction', form_data).then(function(response){
                return response;
            }).catch(function (error){
                return {
                    'status': '0',
                    'msg': error
                };
            })

            if(this.result){
                if(this.result.status == '0'){
                    this.error_message = this.result.data.msg 
                }else{
                    this.error_message = this.result.data.status
                }
            this.login_loading = false;
            }
        }
    }
}
</script>