<template>
    <div>
        <div class="container">

            <div class="row">
                <div class="col-md-6">
                    <table class="table table-striped">
                        <thead>
                            
                            <tr>
                                <th>Name</th>
                                <th>Price</th>
                                <th>qty</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr v-for="product in products" :key="product">
                                <td>{{product.name}}</td>
                                <td>{{product.price}}</td>
                                <td :class="product.qty <10? heightlight:normal">{{product.qty}}</td>
                            </tr>
                        </tbody>
                    </table>
                    <button class="btn btn-primary" @click="calTotal">Total Cost</button>
                    <p>{{total}}</p>
                </div>
                <div class="col-md-6">
                    <form action="" @submit.prevent="addProduct">
                        <div>
                            <label for="" class="form-label mt-3">Product Name</label>
                            <input type="text" name="name" id="" class="form-control" v-model="formData.name">
                        </div>
                        <div>
                            <label for="" class="form-label mt-3">Product Price</label>
                            <input type="text" name="price" id="" class="form-control" v-model="formData.price">
                        </div>
                        <div>
                            <label for="" class="form-label mt-3">Product Qty</label>
                            <input type="text" name="qty" id="" class="form-control" v-model="formData.qty">
                        </div>
                        <div>
                            <button class="btn btn-primary mt-3">Add</button>
                        </div>
                    </form>
                </div>
            </div>

            <div class="row">
                <div class="col-md-6">
                    {{formData.name}},{{formData.price}},{{formData.qty}}
                </div>
            </div>
        </div>

    </div>
</template>

<script>
    export default {
        name:'ProductComponent',
        data()
        {
            return{
                products:[
                    {
                        name:'Noodle',
                        price:'4500',
                        qty:12
                    },
                    {
                        name:'Juice',
                        price:'3000',
                        qty:12
                    },
                    {
                        name:'Coffee',
                        price:'3500',
                        qty:5
                    }
                ], 
                total:0,
                heightlight:'heightlight',
                formData:{
                    name:'',
                    price:'',
                    qty:''
                }
            }
        },
        methods:{
            calTotal()
            {
                this.products.forEach(product => {
                    this.total += (product.price*product.qty)
                });

            },
            addProduct()
            {
                this.products.push(this.formData)
                this.formData={
                    name:'',
                    price:'',
                    qty:''
                }
            }
        }
    }
</script>

<style scoped>
    .heightlight{
        color: red;
    }
</style>