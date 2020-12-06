<template>
    <div>
        <v-row>
            <v-col md="3">
                asdasdasd
            </v-col>
            <v-col md="6">
                asdasd
            </v-col>
            <v-col md="3">
                <div class="sign-in-up-container">
                    <div>
                        <div class="user-icon">
                            <i class="fas fa-user-circle"></i>
                        </div>
                        <div class="welcome">
                            Welcome To Aliba International
                        </div>
                        <div class="button-container mt-6">
                            <v-row>
                                <v-col md="6">
                                    <button class="btn btn-join">Join</button>
                                </v-col>
                                <v-col md="6">
                                    <button class="btn btn-sign-in">Sign In</button>
                                </v-col>
                            </v-row>
                        </div>
                    </div>
                </div>
            </v-col>
        </v-row>
    </div>

</template>

<script>
export default {
name: "CatSliderSign"
}
</script>

<style scoped>
.sign-in-up-container{
    background: rgb(255, 245, 245);
    height: 300px;
    margin: 10px;
    border-radius: 10px;
    text-align: center;
}
.user-icon{
    font-size: 60px;
    color: #fb7a3f;
}
.welcome{
    font-size: 14px;
    color: #000;
    height: 18px;
    overflow: hidden;
    line-height: 18px;
    margin-bottom: 0;
    font-weight: 900;
    font-family: OpenSans-Extrabold,Open Sans,Arial,Helvetica,sans-serif,SimSun;
}
.btn-join{
    width: 80px;
    font-size: 13px;
    color: #fff;
    background-color: #ff4747;
    border-radius: 15px;
    padding: 6px 0;
    float: right;
}
.btn-sign-in{
    width: 80px;
    font-size: 13px;
    color: #fff;
    background-color: #00a040;
    border-radius: 15px;
    padding: 6px 0;
    float: left;
}
.btn-join:hover{
    background-color: #ff5050;
}
.btn-sign-in{
    width: 80px;
    font-size: 13px;
    color: #fff;
    background-color: #00a040;
    border-radius: 15px;
    padding: 6px 0;
    float: left;
}
.btn-sign-in:hover{
    background-color: #00c64f;
}
</style>