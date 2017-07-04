<template>
  <div>
    <div class="wrap">
      <ul v-for="(_item,index) in selectList">
        <p>{{sortInfo[_item]['classify']}}</p>
        <li v-for="item in showList[index]" @click="updateList(index,item)" :class="{'select': item ==_item }"> {{sortInfo[item]['sortName']}}
        </li>
      </ul>
      <div class="button" @click="buy()">提交</div>
    </div>
  </div>
</template>
<script>
export default {
  data () {
    return {
      a: { "code": 1000, "data": { "sortInfo": { "17": { "sortId": "17", "sortName": "\u56db\u5708", "sortDescription": null, "sortCover": null, "price": null, "productId": "7", "sortParent": null, "quantity": null, "classify": "\u8f6e\u6bc2", "productDescription": "\u6b64\u5904\u4e3aE100\u8f66\u8f6e\u5546\u54c1\u7b80\u4ecb", "productName": "E100\u8f66\u8f6e", "sortTree": "17" }, "18": { "sortId": "18", "sortName": "\u9676\u74f7", "sortDescription": null, "sortCover": null, "price": null, "productId": "7", "sortParent": "17", "quantity": null, "classify": "\u8d28\u5730", "productDescription": "\u6b64\u5904\u4e3aE100\u8f66\u8f6e\u5546\u54c1\u7b80\u4ecb", "productName": "E100\u8f66\u8f6e", "sortTree": "17,18" }, "19": { "sortId": "19", "sortName": "\u7070", "sortDescription": null, "sortCover": "\/files\/pics\/51cdda10-e747-5157-f5a2-cd5ba5ff7b95.png", "price": "240000", "productId": "7", "sortParent": "18", "quantity": "995", "classify": "\u989c\u8272", "productDescription": "\u6b64\u5904\u4e3aE100\u8f66\u8f6e\u5546\u54c1\u7b80\u4ecb", "productName": "E100\u8f66\u8f6e", "sortTree": "17,18,19" }, "20": { "sortId": "20", "sortName": "\u84dd", "sortDescription": null, "sortCover": "\/files\/pics\/436c0651-103c-dc61-d5db-f3fce23175b4.png", "price": "240000", "productId": "7", "sortParent": "18", "quantity": "994", "classify": "\u989c\u8272", "productDescription": "\u6b64\u5904\u4e3aE100\u8f66\u8f6e\u5546\u54c1\u7b80\u4ecb", "productName": "E100\u8f66\u8f6e", "sortTree": "17,18,20" }, "23": { "sortId": "23", "sortName": "\u91d1\u5c5e", "sortDescription": null, "sortCover": null, "price": null, "productId": "7", "sortParent": "17", "quantity": null, "classify": "\u8d28\u5730", "productDescription": "\u6b64\u5904\u4e3aE100\u8f66\u8f6e\u5546\u54c1\u7b80\u4ecb", "productName": "E100\u8f66\u8f6e", "sortTree": "17,23" }, "24": { "sortId": "24", "sortName": "\u7070", "sortDescription": null, "sortCover": "\/files\/pics\/7b9329b2-0a2c-7c66-bcbf-e27b7adf3134.png", "price": "200000", "productId": "7", "sortParent": "23", "quantity": "999", "classify": "\u989c\u8272", "productDescription": "\u6b64\u5904\u4e3aE100\u8f66\u8f6e\u5546\u54c1\u7b80\u4ecb", "productName": "E100\u8f66\u8f6e", "sortTree": "17,23,24" }, "25": { "sortId": "25", "sortName": "\u84dd", "sortDescription": null, "sortCover": "\/files\/pics\/e05f4ac1-2973-5943-f513-96cea2bf9004.png", "price": "200000", "productId": "7", "sortParent": "23", "quantity": "1000", "classify": "\u989c\u8272", "productDescription": "\u6b64\u5904\u4e3aE100\u8f66\u8f6e\u5546\u54c1\u7b80\u4ecb", "productName": "E100\u8f66\u8f6e", "sortTree": "17,23,25" }, "28": { "sortId": "28", "sortName": "\u4e94\u5708", "sortDescription": null, "sortCover": null, "price": null, "productId": "7", "sortParent": null, "quantity": null, "classify": "\u8f6e\u6bc2", "productDescription": "\u6b64\u5904\u4e3aE100\u8f66\u8f6e\u5546\u54c1\u7b80\u4ecb", "productName": "E100\u8f66\u8f6e", "sortTree": "28" }, "29": { "sortId": "29", "sortName": "\u9676\u74f7", "sortDescription": null, "sortCover": null, "price": null, "productId": "7", "sortParent": "28", "quantity": null, "classify": "\u8d28\u5730", "productDescription": "\u6b64\u5904\u4e3aE100\u8f66\u8f6e\u5546\u54c1\u7b80\u4ecb", "productName": "E100\u8f66\u8f6e", "sortTree": "28,29" }, "30": { "sortId": "30", "sortName": "\u7070", "sortDescription": null, "sortCover": "\/files\/pics\/2008f4c5-4b54-8b6f-1d74-0971c06712f0.png", "price": "360000", "productId": "7", "sortParent": "29", "quantity": "998", "classify": "\u989c\u8272", "productDescription": "\u6b64\u5904\u4e3aE100\u8f66\u8f6e\u5546\u54c1\u7b80\u4ecb", "productName": "E100\u8f66\u8f6e", "sortTree": "28,29,30" }, "32": { "sortId": "32", "sortName": "\u7c89", "sortDescription": null, "sortCover": "\/files\/pics\/6753f86f-0908-c088-3217-93e891118b5b.png", "price": "360000", "productId": "7", "sortParent": "29", "quantity": "999", "classify": "\u989c\u8272", "productDescription": "\u6b64\u5904\u4e3aE100\u8f66\u8f6e\u5546\u54c1\u7b80\u4ecb", "productName": "E100\u8f66\u8f6e", "sortTree": "28,29,32" }, "33": { "sortId": "33", "sortName": "\u7ea2", "sortDescription": null, "sortCover": "\/files\/pics\/18c1662e-c045-1963-ac65-b42a334f8738.png", "price": "360000", "productId": "7", "sortParent": "29", "quantity": "1000", "classify": "\u989c\u8272", "productDescription": "\u6b64\u5904\u4e3aE100\u8f66\u8f6e\u5546\u54c1\u7b80\u4ecb", "productName": "E100\u8f66\u8f6e", "sortTree": "28,29,33" }, "34": { "sortId": "34", "sortName": "\u91d1\u5c5e", "sortDescription": null, "sortCover": null, "price": null, "productId": "7", "sortParent": "28", "quantity": null, "classify": "\u8d28\u5730", "productDescription": "\u6b64\u5904\u4e3aE100\u8f66\u8f6e\u5546\u54c1\u7b80\u4ecb", "productName": "E100\u8f66\u8f6e", "sortTree": "28,34" }, "35": { "sortId": "35", "sortName": "\u7070", "sortDescription": null, "sortCover": "\/files\/pics\/a633d8a4-a27e-6658-1f66-ee34e687dd24.png", "price": "340000", "productId": "7", "sortParent": "34", "quantity": "1000", "classify": "\u989c\u8272", "productDescription": "\u6b64\u5904\u4e3aE100\u8f66\u8f6e\u5546\u54c1\u7b80\u4ecb", "productName": "E100\u8f66\u8f6e", "sortTree": "28,34,35" }, "37": { "sortId": "37", "sortName": "\u7c89", "sortDescription": null, "sortCover": "\/files\/pics\/612d0ab9-0050-c11b-32a9-1e114c6af44d.png", "price": "340000", "productId": "7", "sortParent": "34", "quantity": "1000", "classify": "\u989c\u8272", "productDescription": "\u6b64\u5904\u4e3aE100\u8f66\u8f6e\u5546\u54c1\u7b80\u4ecb", "productName": "E100\u8f66\u8f6e", "sortTree": "28,34,37" }, "38": { "sortId": "38", "sortName": "\u7ea2", "sortDescription": null, "sortCover": "\/files\/pics\/48751242-1d55-6853-ba0d-bbca004ebac2.png", "price": "340000", "productId": "7", "sortParent": "34", "quantity": "1000", "classify": "\u989c\u8272", "productDescription": "\u6b64\u5904\u4e3aE100\u8f66\u8f6e\u5546\u54c1\u7b80\u4ecb", "productName": "E100\u8f66\u8f6e", "sortTree": "28,34,38" } }, "rankSort": { "17": { "18": { "19": [], "20": [] }, "23": { "24": [], "25": [] } }, "28": { "29": { "30": [], "32": [], "33": [] }, "34": { "35": [], "37": [], "38": [] } } }, "product": { "productId": "7", "productDescription": "\u6b64\u5904\u4e3aE100\u8f66\u8f6e\u5546\u54c1\u7b80\u4ecb", "productName": "E100\u8f66\u8f6e", "successThreshold": null, "successLimit": null, "successCount": "80" } } },
      selectList: [],  // 选择的属性
      showList: []    // 显示的列表
    }
  },
  mounted () {
    this.fillSorts(this.showList, this.selectList, this.rankSort)
  },
  computed: {
    rankSort () { return this.a.data.rankSort },
    sortInfo () { return this.a.data.sortInfo },

  },
  methods: {
    updateList (index, obj) {
      this.selectList.splice(index, 1000, obj)   //删除,并替换最后一个为自己的选择
      this.showList.splice(index + 1, 1000)   //  删除
      this.fillSorts(this.showList, this.selectList, this.getObj(this.rankSort, obj, ''))  //寻找key再将对象处理为数组
    },
    getObj (obj, key, r) {   //遍历obj,找到key所在,遍历出它的对象(不包括key自己),r是保存地
      for (var i in obj) {
        if (i == key) {    //找到key
          r = obj[i];
          break;
        } else if (obj[i].length != 0) {   //没有找到且没有到底部
          r = this.getObj(obj[i], key, r);  //递归
        }
      }
      return r;
    },
    fillSorts (sl, sel, obj) {
      if (obj && obj.constructor === Array) return
      sl.push(Object.keys(obj))  //显示的数据
      sel.push(Object.keys(obj)[0])  //当前选择的节点
      this.fillSorts(sl, sel, obj[Object.keys(obj)[0]])  // 当没有到达底部时,往下递归,将下部分设为默认的第一个
    },
    buy () {
      console.log(`购买的商品id为：${this.selectList}`)
    }
  }
}
</script>
<style lang="scss">
.wrap {
  display: flex;
  flex-direction: column;
  align-items: center;
  ul {
    display: flex;
    p {
      margin: 0 20px 0 0;
    }
    li {
      width: 40px;
      padding: 10px;
      text-align: center;
      list-style: none;
    }
  }
  .select {
    border: 1px solid black;
  }
  .button {
    background: lightcoral;
    margin: 45px 0;
    padding: 5px 10px;
  }
}
</style>
