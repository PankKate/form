<template>
 <div>
  <b-form>

    <b-form-group id="input-name" label="Имя" label-for="input-name">
      <b-form-input
        id="name"
        v-model.trim="name"
        placeholder="Введите имя">
      </b-form-input>
    </b-form-group>

    <b-form-group id="input-surname" label="Фамилия" label-for="input-surname">
      <b-form-input
        id="surname"
        v-model.trim="surname"
        placeholder="Введите фамилию">
      </b-form-input>
    </b-form-group>

    <label for="birthday">Дата рождения</label>
    <b-form-datepicker id="birthday" v-model="birthday" class="mb-2"></b-form-datepicker>
    <p>Дата: '{{ birthday }}'</p>


    <b-form-group id="input-relation" label="Приходится" label-for="input-relation">
      <b-form-select
        id="relation"
        v-model="rel"
        :options="relation"
      ></b-form-select>
    </b-form-group>

    <b-form-group id="input-gifts" label="Подарить" label-for="input-gifts" v-slot="{ ariaDescribedby }">
       <b-form-checkbox-group
          v-model="gifts"
          id="gifts"
          :aria-describedby="ariaDescribedby"
        >
        <b-form-checkbox value="book">Книги</b-form-checkbox>
        <b-form-checkbox value="coffee">Зерна кофе</b-form-checkbox>
        <b-form-checkbox value="sub">Подписку</b-form-checkbox>
        <b-form-checkbox value="money">Деньги</b-form-checkbox>
        <b-form-checkbox value="axe">Боевой топор</b-form-checkbox>
      </b-form-checkbox-group>
    </b-form-group>

    <b-form-group label="Бюджет: " v-slot="{ ariaDescribedby }">
       <b-form-radio v-model="budget" :aria-describedby="ariaDescribedby" name="some-radios" value="min">меньше 800 рублей</b-form-radio>
       <b-form-radio v-model="budget" :aria-describedby="ariaDescribedby" name="some-radios" value="average">от 800 до 2000</b-form-radio>
       <b-form-radio v-model="budget" :aria-describedby="ariaDescribedby" name="some-radios" value="max"> более 2000</b-form-radio>
    </b-form-group>
      
   
  
    <b-form-checkbox id="ready" v-model="giftReady" >Все куплено и готово</b-form-checkbox>

   

  </b-form>
 </div>
</template>

<script>
  import 'bootstrap/dist/css/bootstrap.css'
  import 'bootstrap-vue/dist/bootstrap-vue.css'
  export default {
    data() {
      return {
      
        name: '',
        surname: '',
        birthday: '',
        rel: null,
        giftArr: ['coffee'],
        gifts: [],
        budget: 'average',
        giftReady: false,
        relation: [{ text: 'не выбрано', value: null }, 'другом', 'семьей', 'родственником', 'коллегой', 'знакомым'],
          
      } 
    }
  }
</script>

<style>
html{
  width: 500px;

}
</style>

