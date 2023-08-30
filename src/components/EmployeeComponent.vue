<template>
    <div>

        <div class="container">
            <div class="row">

                <div class="col-md-6">
                    <table class="table table-striped">
                        <thead>
                            
                            <tr>
                                <th>ID</th>
                                <th>Name</th>
                                <th>Department</th>
                                <th>Address</th>
                                <th>Phone</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr v-for="employee in employees" :key="employee">
                                <td>{{employee.id}}</td>
                                <td>{{employee.name}}</td>
                                <td>{{employee.dept}}</td>
                                <td>{{employee.address}}</td>
                                <td>{{employee.phone}}</td>
                            </tr>
                        </tbody>
                    </table>
                </div>

                <div class="col-md-6">
                    <form action="" @submit.prevent="addEmployee">
                        <!-- <div>
                            <label for="" class="form-label mt-3">ID</label>
                            <input type="text" name="id" id="" class="form-control" v-model="formData.id">
                        </div> -->
                        <div>
                            <label for="" class="form-label mt-3">Name</label>
                            <input type="text" name="name" id="" class="form-control" v-model="formData.name" required>
                        </div>
                        <div>
                            <label for="" class="form-label mt-3">Department</label>
                            <input type="text" name="dept" id="" class="form-control" v-model="formData.dept" required>
                        </div>
                        <div>
                            <label for="" class="form-label mt-3">Address</label>
                            <input type="text" name="address" id="" class="form-control" v-model="formData.address" required>
                        </div>
                        <div>
                            <label for="" class="form-label mt-3">Phone</label>
                            <input type="text" name="phone" id="" class="form-control" v-model="formData.phone" required>
                        </div>
                        <div>
                            <button class="btn btn-primary mt-3">Add</button>
                            <button class="btn btn-primary mt-3" @click="deleteEmployee">Delete</button>
                        </div>
                    </form>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name:'EmployeeComponent',
        data(){
            return{
                employees:[
                    
                ],
                formData:
                    {
                        id:'',
                        name:'',
                        dept:'',
                        address:'',
                        phone:''
                    }
                
            }
        },
        methods:{
            addEmployee()
            {
                this.formData.id=this.employees.length+1
                this.employees.push(this.formData)
                this.formData={
                    id:this.employees.length+1,
                    name:'',
                    dept:'',
                    address:'',
                    phone:''
                }
            },
            deleteEmployee()
            {
                this.employees.pop()
            }
        }
    }
</script>

<style scoped>

</style>