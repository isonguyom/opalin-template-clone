<template>
    <main :class="{active: isActive}">
        <div class="login-img">
            <button class="close-btn" @click="$emit('close-modal')">X</button>
        </div>
        <div class="login-form-wrapper">
            <p class="login-title">Welcome back.</p>
            <p class="login-text">Enter your details below.</p>
            <form action="">
                <div class="el-wrapper">
                    <label for="loginEmail">Email:</label>
                    <input type="email" name="loginEmail" id="loginEmail">
                </div>
                <div class="el-wrapper">
                    <span><a href="" class="faint-text forgot">Forget password?</a></span>
                    <label for="loginPassword">Password:</label>
                    <input type="password" name="loginPassword" id="loginPassword">
                </div>
                <div class="el-wrapper checkbox-wrapper">
                    <input type="checkbox" name="loginRememberMe" id="loginRememberMe">
                    <label for="loginRememberMe">Remember Me</label>
                </div>

                <button class="submit-btn" type="submit">Login</button>
                <p class="bottom-text"><span class="faint-text">Don't have an account?</span> <a class="signup-link" href="">Sign Up</a></p>
            </form>
        </div>
    </main>
</template>

<script>
export default {
    props: ['isActive'],
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

.login-img {
    background: url('../assets/images/login-bg.jpg');
    height: 180px;
    background-size: cover;
    padding: 20px 2%;
    text-align: right;
}

.login-img .close-btn {
    width: 60px;
    height: 60px;
    border-radius: 50%;
    border: 0;
    margin-right: 0;
    cursor: pointer;
    font-size: 1.1rem;
}

.login-form-wrapper {
    padding: 45px 5%;
}

.login-title {
    font-weight: 600;
    font-size: 1.2rem;
    margin-bottom: 20px;
}

.login-text {
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
.el-wrapper input[type="password"] {
    width: 100%;
    border-radius: 5px;
    padding: 13px;
    background: #f6f6f9;
    border: 1px solid #ececee;
    border-radius: 7px;
}

.forgot {
    text-decoration: none;
    color: #110F24;
    float: right;
    z-index: 1;
    width: fit-content;
}

.el-wrapper.checkbox-wrapper input {
    width: 30px;
}

.el-wrapper.checkbox-wrapper label {
    display: inline-block;
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

    .login-img {
        order: 2;
    }

    .login-text {
        font-size: 1.3rem;
    }
}
</style>