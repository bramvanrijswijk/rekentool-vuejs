<template>
    <div class="flex items-center mb-2">
        <span class="w-2/12 text-right pr-4">
          {{ this.calculation.firstDigit + ' ' + this.calculation.operator + ' ' + this.calculation.secondDigit }} =
        </span>
        <input
            v-model.number="userAnswer"
            class="w-10/12 border-2 border-gray-300 flex-grow p-2"
            type="text"
            v-bind:class="[answerIsCorrect ? 'border-green-400' : 'border-gray-300']"
            @keyup="checkIfAnswerIsCorrect"
        >
    </div>
</template>

<script>
import _ from 'lodash';

export default {
    data() {
        return {
            calculation: this.generateCalculation(),
            userAnswer: null,
            answerIsCorrect: false
        }
    },

    methods: {
        generateCalculation() {
            const operators = ['+', '-', '*'];
            const chosenOperator = _.sample(operators);

            let digitRange = [2, 12];
            if (chosenOperator === '+' || chosenOperator === '-') {
                digitRange = [20, 100];
            }

            let firstDigit = _.random(digitRange[0], digitRange[1], false);
            let secondDigit = _.random(digitRange[0], digitRange[1], false);

            let answer = 0;
            switch (chosenOperator) {
                case '+':
                    answer = firstDigit + secondDigit;
                    break;

                case '-':
                    answer = firstDigit - secondDigit;
                    break;

                default:
                    answer = _.multiply(firstDigit, secondDigit);
            }

            return {
                firstDigit: firstDigit,
                operator: chosenOperator,
                secondDigit: secondDigit,
                answer: answer
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