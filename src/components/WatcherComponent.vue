<template>
    <div>
        

        <div class="container">
            <div class="row">
                <div class="col-md-4">
                    Stock level 1: {{ stock }}
                    <button class="btn btn-success" @click="$event => stock++">Stock In</button>
                    <button class="btn btn-warning" @click="$event => stock--">Stock Out</button>
                </div>

                <div class="col-md-4">
                    <form action="">
                        <div>
                            <label for="" class="form-label">Your Name</label>
                            <input type="text" name="name" class="form-control" v-model="studentData.name">
                        </div>
                        <div class="mt-3">
                            <label for="" class="form-label">Your Age</label>
                            <input type="number" name="age" class="form-control" v-model="studentData.age">
                        </div>
                    </form>
                </div>

                <div class="col-md-4">
                    Mark (1-100) : {{ mark }}
                    <button class="btn btn-success" @click="$event => mark++">Mark Increase</button>
                </div>
            </div>
        </div>

    </div>
</template>

<script>
    export default {
        name:'WatcherComponent',
        data()
        {
            return{
                stock:10,
                studentData:{
                    name:'',
                    age:''
                },
                mark:101
            }
        },
        watch:{

            //Lazy Watch
            stock(newStock,oldStock) //equal with the variable name we will watch
            {
                if(newStock>=20 && newStock>oldStock)
                {
                    alert("Your stock level is high!")
                }
                if(newStock<5)
                {
                    alert("Your stock level is low")
                }
            },

            //Deep Watch
            studentData:{
                handler(newValue)
                {
                    if(newValue.age>25)
                    {
                        alert("you are old for undergraduate")
                    }
                },
                deep:true
            },

            //Eager Watch
            mark:
            {
                handler(newMark)
                {
                    if(newMark>100)
                    {
                        alert("out of range!")
                    }
                },
                immediate:true
            }

        }
    }
</script>

<style scoped>

</style>