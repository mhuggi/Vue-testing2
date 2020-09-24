<template>
    <div class="mt-5 text-primary">
        <h5>Fråga 1</h5>
        <p>{{ currentQ.q }}</p>
        <div class="link-container text-danger mt-3">
            <p  @click="checkA(index)" v-for="(answer,index) in currentQ.a" :key="index" class="btn btn-outline-primary btn-lg m-3">
                <a>{{answer}}</a>
            </p>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Quiz",

        props: {
            currentQ: Object
        },
        methods: {
            checkA(i) {
                this.$emit('answered', i)
            },
        }
    }
</script>