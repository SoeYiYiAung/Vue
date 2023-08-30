<template>
    <div>
        <div class="container">
            <div class="row">
                <div class="col-md-4">
                    <div class="row">
                        <div class="col-md-6">
                            <label for="" class="form-label mt-3">Name</label>
                            <input type="text" name="name" id="" class="form-control" required v-model="formData.name" >
                        </div>
                        <div class="col-md-6">
                            <label for="" class="form-label mt-3">Email</label>
                            <input type="email" name="email" id="" class="form-control" required v-model="formData.email">
                        </div>
                        <div class="col-md-12">
                            <label for="" class="form-label mt-3">Phone</label>
                            <input type="phone" name="phone" id="" class="form-control" required v-model="formData.phone">
                        </div>

                        <div class="col-md-12 mt-3">
                            <button class="btn btn-primary mx-3" @click="create">Create</button>
                            <button class="btn btn-primary mx-3" @click="update()">Update</button>
                        </div>
                    </div>
                </div>

                <div class="col-md-8">
                    <table class="table table-striped">
                        <thead>                            
                            <tr>
                                <th>Name</th>
                                <th>Email</th>
                                <th>Phone</th>
                                <th>Actions</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr v-for="employee,index in employees" :key="employee">
                                <td>{{employee.name}}</td>
                                <td>{{employee.email}}</td>
                                <td>{{employee.phone}}</td>
                                <td>                                    
                                    <button class="btn btn-success mx-3" @click="edit(employee,index)">Edit</button>
                                    <button class="btn btn-warning mx-3" @click="destroy(index)">Delete</button>
                                    <button class="btn btn-danger mx-3" @click="view(employee)">View</button>
                                </td>
                            </tr>
                        </tbody>
                    </table>
                </div>

            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name:'CrudComponent',
        data(){
            return{
                employees:[

                ],
                formData:{
                    name:'',
                    email:'',
                    phone:'',                    
                },
                index:''
            }
        },
        methods:{
            create()
            {
                this.employees.push(this.formData)
                this.formData={
                    name:'',
                    email:'',
                    phone:''
                }
            }
            ,
            destroy(index)
            {                
                // employee.remove();
                this.employees.splice(index,1);
            },            
            view(employee)
            {
                // console.log(employee)
                this.formData={
                    name:employee.name,
                    email:employee.email,
                    phone:employee.phone
                }
            },

            edit(employee,index)
            {                
                // this.employees.splice(employee, 1);
                this.index=index
                this.formData={
                    name:employee.name,
                    email:employee.email,
                    phone:employee.phone
                }
                return employee
            },
            
            update()
            {
                this.formData={
                    name:this.formData.name,
                    email:this.formData.email,
                    phone:this.formData.phone
                }
                this.employees[this.index]=this.formData

                this.formData={
                    name:'',
                    email:'',
                    phone:''
                }
            }
        }
    }
</script>

<style scoped>

</style>