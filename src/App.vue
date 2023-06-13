<template>
  <main>
    <!-- 
      Direktif v-if digunakan untuk membuat blok secara kondisional. 
      Blok hanya akan dirender jika ekspresi direktif mengembalikan nilai true. 
    -->
    <ol v-if="isShowList">
      <!-- 
        Kita dapat menggunakan direktif v-for untuk merender daftar item berdasarkan array. 
        Direktif v-for memerlukan sintaks khusus dalam bentuk item dalam listItem, 
        di mana listItem adalah larik data sumber dan item adalah alias untuk elemen larik yang sedang diiterasi 
      -->
      <li v-for="item in listItem" :key="item.id">{{ item.name }}</li>
    </ol>
    <!-- 
      Direktif v-else digunakan untuk membuat else blok. atau 
      dapat juga digunakan <div v-else-if="condition"></div>
    -->
    <div v-else>
      List is not visible
    </div>

    <br>
    <button @click="changeCondition(true)">Show List!</button> 
    <button v-if="isShowList" @click="changeCondition(false)" style="margin-left: 20px;">Hide List!</button>
  </main>
</template>

<script>

export default {
  data() {
    return {
      isShowList: false,
      listItem: [
        {
          id: 1,
          name: "Item 01"
        },
        {
          id: 2,
          name: "Item 02"
        },
        {
          id: 3,
          name: "Item 03"
        }
      ]
    }
  },
  methods: {
    changeCondition(condition) {
      this.isShowList = condition
    }
  }
}

</script>

