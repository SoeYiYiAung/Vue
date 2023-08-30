<template>
    <div>

        <div class="container">
            <div class="row">
                <div class="col-md-6">
                    <form action="" @submit.prevent="addStudent">
                        <div>
                            <label for="" class="form-label">Your Name</label>
                            <input type="text" name="name" class="form-control" v-model="studentData.name">
                        </div>
                        <div class="mt-3">
                            <label for="" class="form-label mt-3">Your Age</label>
                            <input type="number" name="age" class="form-control" v-model="studentData.age">
                        </div>
                        <div>
                            <label for="" class="form-label mt-3">Your Email</label>
                            <input type="email" name="email" class="form-control" v-model="studentData.email">
                        </div>
                        <div>
                            <button class="btn btn-primary mt-3">Add Student</button>
                        </div>
                    </form>
                </div>

                <div class="col-md-6">
                    <ChildComponentVue :students="students" @count="total" @filter="filterData"></ChildComponentVue>
                </div>
            </div>

            <div class="row mt-5">
                <div class="col-md-6" v-show="filters.length>0">
                    <table class="table table-bordered">
                        <thead>
                            <tr>
                                <th>Name</th>
                                <th>Email</th>
                                <th>Age</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr v-for="item in filters" :key="item">
                                <td>{{item.name}}</td>
                                <td>{{item.email}}</td>
                                <td>{{item.age}}</td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>
        </div>

    </div>
</template>

<script>
import ChildComponentVue from './ChildComponent.vue'
export default {
        name:'ParentComponent',
        components:
        {
            ChildComponentVue
        },
        data()
        {
            return{
                studentData:{
                    name:'',
                    age:'',
                    email:''
                },
                students:[

                ],
                filters:[

                ]
            }
        },
        methods:
        {
            addStudent()
            {                
                this.students.push(this.studentData),
                this.studentData={
                    name:'',
                    age:'',
                    email:''
                }
            },
            total(num_student)
            {
                console.log("Number of students is "+num_student)
            },
            filterData(students_filter)
            {
                console.log(students_filter)
                this.filters=students_filter
            }

        }
    }
</script>

<style scoped>

</style>