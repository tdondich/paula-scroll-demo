<template>
    <div>
        <ul>
            <li :key="idx" v-for="(data, idx) in log">
                {{data}}
            </li>
        </ul>
    </div>
</template>

<script>
export default {
  props: ['log']
}
</script>

<style lang="scss">

</style>
