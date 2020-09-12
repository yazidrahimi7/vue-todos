<template>
    <div>
        <div class="alert alert-info" role="alert">
            <slot></slot>
        </div>
    </div>
</template>

<script>
</script>

<style scoped>
    .alert {
        cursor: pointer;
        margin: 5px;
    }
    .alert:hover {
        background-color: #f86e6e
    }
</style>