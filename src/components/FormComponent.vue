<template>
    <div>
       
        <div class="container ">

            <div class="row mt-3">
                <div class="col-md-6 bg-secondary">
                    <form action="" @submit.prevent="addNewCustomer">

                        <div class="row">
                            <div class="col-md-6">
                                <label for="" class="form-label mt-3">First Name</label>
                                <input type="text" name="first_name" id="" class="form-control" v-model="formData.first_name">
                            </div>
                            <div class="col-md-6">
                                <label for="" class="form-label mt-3">Last Name</label>
                                <input type="text" name="last_name" id="" class="form-control" v-model="formData.last_name">
                            </div>
                        </div>

                        <div class="row">
                            <div class="col-md-6">
                                <label for="" class="form-label mt-3">Contact Number</label>
                                <input type="phone" name="contact_number" id="" class="form-control" v-model="formData.contact_number">
                            </div>
                            <div class="col-md-6">
                                <label for="" class="form-label mt-3">Email</label>
                                <input type="email" name="email" id="" class="form-control" v-model="formData.email">
                            </div>
                        </div>

                        <div class="row mt-3">
                            <label for="" class="form-label mt-3"><b>I am a</b></label>

                            <div class="col-md-6">
                                <input type="radio" name="customer" id="" class="form-check-input" value="new" v-model="formData.customer"> New Customer
                            </div>
                            <div class="col-md-6">
                                <input type="radio" name="customer" id="" class="form-check-input" value="existing" v-model="formData.customer"> Existing Customer
                            </div>
                        </div>

                        <div class="row mt-3">
                            <label for="" class="form-label mt-3"><b>I need a solution for</b></label>

                            <div class="col-md-6">
                                <input type="radio" name="solution" id="" class="form-check-input" value="home" v-model="formData.solution"> Home
                            </div>
                            <div class="col-md-6">
                                <input type="radio" name="solution" id="" class="form-check-input" value="business" v-model="formData.solution"> Business
                            </div>
                        </div>

                        <div class="row">
                            <div class="col-md-12">
                                <label for="" class="form-label mt-3">My Indestry is</label>
                                <select class="form-select" name="indestry" id="" v-model="formData.indestry">
                                    <option value="1">One</option>
                                    <option value="2">Two</option>
                                    <option value="3">Three</option>
                                </select>
                            </div>
                        </div>

                        <div class="row mt-5">
                            <label for="" class="form-label mt-3"><b>The services I am interested in are</b></label>
                            
                            <div class="col-md-6 form-check">
                                <input class="form-check-input" type="checkbox" value="check1" id="" name="service" v-model="formData.service">
                                <label class="form-check-label" for="flexCheckDefault">
                                    Default checkbox
                                </label>
                            </div>
                            <div class="col-md-6 form-check">
                                <input class="form-check-input" type="checkbox" value="check2" id="" name="service" v-model="formData.service">
                                <label class="form-check-label" for="flexCheckChecked">
                                    Checked checkbox
                                </label>
                            </div>
                            <div class="col-md-6 form-check">
                                <input class="form-check-input" type="checkbox" value="check3" id="" name="service" v-model="formData.service">
                                <label class="form-check-label" for="flexCheckDefault">
                                    Default checkbox
                                </label>
                            </div>
                            <div class="col-md-6 form-check">
                                <input class="form-check-input" type="checkbox" value="check4" id="" name="service" v-model="formData.service">
                                <label class="form-check-label" for="flexCheckChecked">
                                    Checked checkbox
                                </label>
                            </div>
                        </div>

                        <div>
                            <button class="btn btn-primary mt-3">Add</button>
                        </div>
                    </form>
                </div>


                <div class="col-md-6">
                    <table class="table table-striped">
                        <thead>
                            
                            <tr>
                                <th>First Name</th>
                                <th>Last Name</th>
                                <th>Contact Number</th>
                                <th>Email</th>
                                <th>Customer</th>
                                <th>Solution</th>
                                <th>Indestry</th>
                                <th>Services</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr v-for="customer in customers" :key="customer">
                                <td>{{customer.first_name}}</td>
                                <td>{{customer.last_name}}</td>
                                <td>{{customer.contact_number}}</td>
                                <td>{{customer.email}}</td>
                                <td>{{customer.customer}}</td>
                                <td>{{customer.solution}}</td>
                                <td>{{customer.indestry}}</td>
                                <td>{{customer.service}}</td>
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
        name:'FormComponent',
        data()
        {
            return{
                customers:
                [
                                    
                ],
                formData:{
                    first_name:'',
                    last_name:'',
                    contact_number:'',
                    email:'',
                    customer:'',
                    solution:'',
                    indestry:'',
                    service:[]
                }
                
            }
        },
        methods:{
            addNewCustomer()
            {
                this.customers.push(this.formData)
                this.formData={
                    first_name:'',
                    last_name:'',
                    contact_number:'',
                    email:'',
                    customer:'',
                    solution:'',
                    indestry:'',
                    service:[]
                }
            }
        }
    }
</script>

<style scoped>

</style>