<script>
    export default { 
        // Add Code Here to complete the task
        // Note: DO NOT USE "eval()". In security, "eval" is considered "evil"!!!

        data(){
            return {
                x: 0,
                y: 0,
                selectedOp: '+',
                operators: [
                    '+', '-', '*', '/', '%'
                ]
            }
        },
        computed: {
            result() {
                const a = this.x
                const b = this.y
                const op = this.selectedOp

                if (op === '+'){
                    return a + b
                }
                else if (op === '-'){
                    return a - b
                }
                else if (op === '*'){
                    return a * b
                }
                else if (op === '/'){
                    return b !== 0 ? a / b : 'Error'
                }
                else if (op === '%'){
                    return b !== 0 ? a % b : 'Error'
                }
                else{
                    return 'Invalid operator'
                }
            }
        }
    }
</script>

<template>
    <p>x <input v-model.number="x"></p>
    <select v-model="selectedOp">
        <option v-for="op in operators" >{{ op }}</option>
    </select>
    <p>y <input v-model.number="y"></p>
    
    <p>---------------------</p>

    <p>= {{result}}</p>
</template>

<style scoped>
    p, input { font-family: monospace; }
    p { white-space: pre; }

</style>
