<template>
    <div>
        {{pengulangan}}
    </div>
</template>

<script>
export default {
    props: {
        pengulangan: {
            type: String,
            default: ''
        }
    }
}
</script>