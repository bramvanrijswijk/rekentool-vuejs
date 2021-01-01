<template>
    <div class="flex items-center mb-2">
        <span class="w-2/12 text-right pr-4">{{ this.calculation['calculation'][0] + ' ' + this.calculation['calculation'][1] + ' ' + this.calculation['calculation'][2] }} = </span>
        <input
            type="text"
            class="w-10/12 border-2 border-gray-300 flex-grow p-2"
            v-bind:class="[answerIsCorrect ? 'border-green-400' : 'border-gray-300']"
            v-model.number="userAnswer"
            @keyup="checkIfAnswerIsCorrect()"
        >
    </div>
</template>

<script>
    import _ from 'lodash';

    export default {
        name: "Calculation",
        data() {
            return {
                'calculation': this.generateCalculation(),
                'userAnswer': null,
                'answerIsCorrect': false
            }
        },
        methods: {
            generateCalculation() {
                let firstDigit = _.random(0, 10, false);
                let secondDigit = _.random(0, 10, false);

                return {
                    'calculation': [firstDigit, 'x', secondDigit],
                    'answer': _.multiply(firstDigit, secondDigit)
                }
            },
            checkIfAnswerIsCorrect() {
                this.answerIsCorrect = (this.calculation.answer === this.userAnswer);
            }
        }
    }
</script>

<style scoped>

</style>