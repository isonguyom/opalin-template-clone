<template>
    <main :class="{active: isActive}">
        <div class="signup-img">
            <button class="close-btn" @click="$emit('close-modal')">X</button>
        </div>
        <div class="signup-form-wrapper">
            <p class="signup-title">Welcome!</p>
            <p class="signup-text">Enter your details to create an account.</p>
            <form action="">
                <div class="el-wrapper">
                    <label for="signupName">Name:</label>
                    <input type="text" name="signupName" id="signupName">
                </div>
                <div class="el-wrapper">
                    <label for="signupEmail">Email:</label>
                    <input type="email" name="signupEmail" id="signupEmail">
                </div>
                <div class="el-wrapper">
                    <label for="signupPassword">Password:</label>
                    <input type="password" name="signupPassword" id="signupPassword">
                </div>

                <button class="submit-btn" type="submit">Create Account</button>
                <p class="bottom-text"><span class="faint-text">By creating an account, you agree to our</span> <a class="signup-link" href="">Terms.</a></p>
                <p class="bottom-text"><span class="faint-text">Already have an account?</span> <a class="signup-link" href="">Log In</a></p>
            </form>
        </div>
    </main>
</template>

<script>
export default {
    props:['isActive'],
    emits: ['close-modal'],
}
</script>

<style scoped>
main {
    background-color: white;
    min-height: 100vh;
    z-index: 100;
    width: 100%;
    position: fixed;
    display: none;
}

.signup-img {
    background: url('../assets/images/signup-bg.jpg');
    height: 180px;
    background-size: cover;
    padding: 20px 2%;
    text-align: right;
}

.signup-img .close-btn {
    width: 60px;
    height: 60px;
    border-radius: 50%;
    border: 0;
    margin-right: 0;
    cursor: pointer;
    font-size: 1.1rem;
}

.signup-form-wrapper {
    padding: 45px 5%;
}

.signup-title {
    font-weight: 600;
    font-size: 1.2rem;
    margin-bottom: 20px;
}

.signup-text {
    margin-bottom: 30px;
}

.faint-text {
    opacity: 0.5;
}

.el-wrapper {
    margin-bottom: 30px;
    width: 100%;
}

.el-wrapper label {
    display: block;
    margin-bottom: 7px;
    font-weight: 600;
}

.el-wrapper input[type="email"],
.el-wrapper input[type="password"], .el-wrapper input[type="text"] {
    width: 100%;
    border-radius: 5px;
    padding: 13px;
    background: #f6f6f9;
    border: 1px solid #ececee;
    border-radius: 7px;
}


.submit-btn {
    width: 100%;
    padding: 15px 20px;
    height: 50px;
    text-transform: capitalize;
    border: 0;
    border-radius: 50px;
    font-weight: 600;
    font-size: 1rem;
    cursor: pointer;
    margin-bottom: 30px;
    background-color: #575BDE;
    color: #fff;
}

.bottom-text {
    text-align: center;
    line-height: 25px;
}

.signup-link {
    color: #575BDE;
    text-decoration: none;
}

main.active {
    display: block;
}



@media screen and (min-width: 768px) {
    main.active {
        display: flex;
    }

    main>div {
        width: 50%;
        min-height: 100vh;
    }

    .signup-img {
        order: 2;
    }

    .signup-text {
        font-size: 1.3rem;
    }
}
</style>