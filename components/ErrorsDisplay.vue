<template>
    <div>
        <h2 class="validation">Validation errors</h2>
        <div class="panel--centered">
            <ul>
                <li class="validation" v-for="(error,index) in errors" :key="index">
                    {{ error }}
                </li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
    props: ['errors']
}
</script>