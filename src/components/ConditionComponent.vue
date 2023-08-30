<template>
    <div>
        <h2>Name is {{name}}</h2>
        <p v-if="age>30">Second Level</p>
        <p v-else-if="age<30">Young Person</p>

        <p v-if="mark>80">Grade-A</p>
        <p v-else-if="mark>=65 && mark<80">Grade-B</p>
        <p v-else-if="mark>=50 && mark<65">Grade-C</p>
        <p v-else>Grade-D</p>

    <div class="container">
        <div class="row">
            <div class="col-md-6">
                <img src="../assets/logo.png" alt="" v-if="isShow==true">
            </div>
            <div class="col-md-6" v-show="isShow">
                <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quidem facilis quaerat, consequuntur alias, autem eos necessitatibus velit vero doloremque natus vitae aspernatur possimus non dolorum hic totam libero voluptas aliquam?</p>
            </div>
        </div>

        <div class="row">
            <div class="col-md-6">
                <ul>
                    <li v-for="(item,index) in subjects" :key="item">
                        {{index+1}} : {{item}}
                    </li>
                </ul>
                <button @click="calTotal" class="btn btn-primary">Calculate Total</button>
                <h2>Total Mark is {{total}}</h2>
            </div>

            <div class="col-md-6">
                <button @click="calAverage" class="btn btn-primary">Calculate Average</button>
                <h2>Average Mark is {{average}}</h2>
            </div>
        </div>

        <div class="row">
            <div class="col-md-6">
                <li v-for="(item) in subjects" :key="item">
                    Mark : {{item}}  

                    <button @click="calGrade(item)" class="btn btn-primary">Calculate Grade</button>
                    <h6>Grade is {{grade}}</h6>
                </li>
                
            </div>


            <div class="col-md-6">
                <p v-for="item,index in students" :key="item">
                    {{index}} : {{item}}
                </p>
            </div>

        </div>


        <div class="row">
            <div class="col-md-6">
                <table>
                    <tr v-for="emp in employees" :key="emp">
                        <td v-for="item,index in emp" :key="item">
                            {{index}} : {{item}}
                        </td>
                    </tr>
                </table>
            </div>

            <div class="col-md-6">
                <table>
                    <tr v-for="emp in employees" :key="emp">
                        <td v-for="item in emp" :key="item">
                            {{item}}
                        </td>
                    </tr>
                </table>
            </div>
        </div>
    </div>

    </div>
</template>

<script>
    export default {
        name:'ConditionComponent',
        data()
        {
            return{
                name:'Ahn Hyo Seop',
                age:35,
                mark:99,
                isShow:true,
                subjects:[75,80,99,86,78,90],
                total:0,
                average:0,
                grade:'',

                students:{
                    name:"David",
                    major:"IT",
                    address:"Mandalay"
                },

                employees:[
                    {
                    name:"David0",
                    major:"IT",
                    address:"Mandalay"
                    },{
                        name:"David1",
                        major:"IT",
                        address:"Mandalay"
                    },{
                        name:"David2",
                        major:"IT",
                        address:"Mandalay"
                    },{
                        name:"David3",
                        major:"IT",
                        address:"Mandalay"
                    },
                ]
            }
        },
        methods:{
            calTotal()
            {
                for(let i=0;i<this.subjects.length;i++)
                {
                    this.total=this.total+this.subjects[i]
                    console.log(this.total)
                }
            },
            calGrade(item)
            {
                if(this.item>80)
                    {
                        this.grade='A'
                    }
                    else if(item>60)
                    {
                        this.grade='B'
                    }
                    else if(item>40)
                    {
                        this.grade='C'
                    }
                    else
                    {
                        this.grade='D'
                    }
            }
            ,
            calAverage()
            {
                this.calTotal()
                this.average=this.total/this.subjects.length

            }
        }
    }
</script>

<style scoped>

</style>