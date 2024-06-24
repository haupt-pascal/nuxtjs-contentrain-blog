<script setup>
</script>
<template>
    <div class="navigation">
        <div class="navigation__left">
            <a href="/">
                <img alt="Logo" class="navigation__logo">
            </a>
        </div>
        <div class="navigation__right">
            <a href="/blog">Blog</a>
            <a href="/contact">Contact</a>
        </div>
    </div>
</template>
<style lang="scss" scoped>
.navigation {
    height: 10vh;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 5%;

    .navigation__left {

    }

    .navigation__right {
        a {
            margin-left: 20px;
            color: white;
            text-decoration: none;
        }
    }
}
</style>