<template>
    <button :style="{ backgroundColor: bgColor, color: textColor, width: btnWidth + '%' }">{{ text }}</button>
</template>

<script>
export default {
    props: ['text', 'bgColor', 'textColor', 'btnWidth']
}
</script>

<style scoped>
button {
    padding: 15px 20px;
    height: 50px;
    text-transform: capitalize;
    border: 0;
    border-radius: 50px;
    font-weight: 600;
    font-size: 1rem;
    cursor: pointer;
}
</style>