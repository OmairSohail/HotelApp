<template>
<div>
    <OnlyNavbar/>
    <div class="container">
        <br>
        <br>
        <br>
    <b-table :data="data" :columns="columns"></b-table>
    </div>
    <div class="Userlists">
      <ul>
          <li></li>
      </ul>
    </div>
</div>
</template>

<script>
import {db} from '../plugins/firebase'
import OnlyNavbar from '../components/OnlyNavbar'
    export default {
        components:{
           OnlyNavbar
        },
        data() {
            return {
                data: [
                ],
                columns: [
                    {
                        field: 'id',
                        label: 'ID',
                        width: '40',
                        numeric: true
                    },
                    {
                        field: 'Username',
                        label: 'Username',
                    },
                    {
                        field: 'Email',
                        label: 'Email',
                    },
                    {
                        field: 'Date',
                        label: 'Date',
                        centered: true
                    },
                    {
                        field: 'Password',
                        label: 'Password',
                    }
                ]
            }
        },
        created(){
           db.collection('Users').get()
                .then((snapshot) => {
                    snapshot.forEach((doc) => {
                        //Data Object
                    const data = {
                      "id":doc.data().User_ID,
                      "Username":doc.data().Username,
                      "Email":doc.data().Email,
                      "Date":doc.data().Create_At,
                      "Password":doc.data().Password
                    }
                    this.data.push(data)
                    
                    //console.log(doc.id, '=>', doc.data());
                    });
                })
                .catch((err) => {
                    console.log('Error getting documents', err);
                });
        }
    }
</script>

<style scoped>

</style>