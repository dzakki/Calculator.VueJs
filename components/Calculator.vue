<template>
	<div id="wrapper">
        <div id="calculator">
            <legend><h2>Calculator</h2></legend>
            <table border="0" cellspacing='3'>
                <thead>
                    <tr>
                        <td colspan="4"> <input type="text" id="input" maxlength="18" readonly v-model="results" /></td>
                        <td><button class="hapus" @click="remove()" >&lt;</button></td>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td><button class="angka" @click="add('7')">7</button></td>
                        <td><button class="angka" @click="add('8')">8</button></td>
                        <td><button class="angka" @click="add('9')">9</button></td>
                        <td colspan="2"><button class="ac" @click="clear()">AC</button></td>
                    </tr>
                    <tr>
                        <td><button class="angka" @click="add('4')">4</button></td>
                        <td><button class="angka" @click="add('5')">5</button></td>
                        <td><button class="angka" @click="add('6')">6</button></td>
                        <td><button class="operasi" @click="add('+')">+</button></td>
                        <td><button class="operasi" @click="add('-')">-</button></td>
                    </tr>
                    <tr>
                        <td><button class="angka" @click="add('1')">1</button></td>
                        <td><button class="angka" @click="add('2')">2</button></td>
                        <td><button class="angka" @click="add('3')">3</button></td>
                        <td><button class="operasi" @click="add('*')">x</button></td>
                        <td><button class="operasi" @click="add('/')">/</button></td>
                    </tr>
                    <tr>
                        <td><button class="operasi" @click="add('%')">%</button></td>
                        <td><button class="angka" @click="add('0')">0</button></td>
                        <td><button class="angka" @click="add('.')">.</button></td>
                        <td colspan="2"><button class="hasil" @click="resultAll()">=</button></td>
                    </tr>
                </tbody>
            </table>
        </div>
    </div>
</template>
<script>
	export default{
        data: function(){
            return {
                results: "",
            }
        },
        methods:{
            remove(){
                this.results = this.results.slice(0, -1)
            },
            add(val){
                if (val === "%") {
                    return this.results = eval(this.results) / 100
                }
                return this.results += val
            },
            clear(){
                this.results = ""  
            },
            resultAll(){
                this.results = eval(this.results)
            }
        }
	}
</script>