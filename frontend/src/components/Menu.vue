<template>
    <nav class="navbar navbar-expand-lg bg-body-tertiary">
        <div class="container-fluid">
            <a class="navbar-brand" href="#">
                <img class="logo" src="/img/logo.jpeg" alt="Assembleia de Deus Redenção">
            </a>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
            </button>
        </div>
    </nav>
</template>

<script>
export default {
    name: 'Menu',
}
</script>

<style scoped>
.navbar {
    margin-bottom: 10px;
}
.logo {
    width: 70px;
    height: 70px;
}
</style>
