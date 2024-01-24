<template>
    <Layout title="健康檢查調查表">
      <template #content>
        <div class="flex flex-col space-y-8">
          <!-- 個人疲勞 -->
          <div>
            <h3 class="pl-4 mb-4 text-lg border-l-8 border-black md:text-2xl">
                基本資料
            </h3>
            <div class="grid grid-cols-2 gap-x-8 gap-y-6">
                <Input label="姓名" placeholder="請輸入姓名"/>
                <Input label="性別" :showCheckButton="true" :showInput="false" :buttonLabels="['男', '女']" />
                <Input label="身分證字號 (護照號碼)" placeholder="請輸入身分證字號" :showInput="true" />
                <Input label="出生日期" placeholder="請輸入姓名" :showInput="false" :showDateInput="true"/>
                <Input label="受僱日期（公司團體專用）" placeholder="請輸入姓名" :showInput="false" :showDateInput="true" />
                <Input label="E-MAIL" placeholder="請輸入E-MAIL"/>
                <Input label="電話（公）" placeholder="請輸入電話" />
                <Input label="電話（家）" placeholder="請輸入電話" />
                <Input label="電話（行動）" placeholder="請輸入電話" />
                <Input label="通訊地址" placeholder="請輸入地址" class="col-span-2"/>
            </div>
          </div>
  
          <div class="w-full border-t border-gray-300" />
  
          <!-- 工作疲勞 -->
          <div>
            <h3 class="pl-4 mb-4 text-lg border-l-8 border-black md:text-2xl">
                作業經歷(公司團體專用)
            </h3>
            <ol class="space-y-6 list-decimal list-inside md:text-lg">
                <li>
                    曾經從事的(前一份工作)<Input />
                    <div class="grid items-center mt-2 md:grid-cols-2 gap-x-6 gap-y-2 whitespace-nowrap">
                        <div>起始日期：<Date /></div>
                        <div>截止日期：<Date /></div>
                    </div>
                </li>
                <li>
                    目前從事<Input />
                    <div class="grid items-center mt-2 md:grid-cols-2 gap-x-6 gap-y-2 whitespace-nowrap">
                        <div>起始日期：<Date /></div>
                        <div>截止日期：<Date /></div>
                        <Input label="是否需輪班" :showCheckButton="true" :showInput="false" :buttonLabels="['兩班制', '三班制', '四班制', '其他', '否']" />
                    </div>
                    
                </li>
            </ol>
          </div>
        </div>
  
        <Confirm />
      </template>
    </Layout>
  </template>
  
  <script>
  export default {
    data() {
      return {
        person: [
          { id: 1, title: '你常覺得疲勞嗎?' },
          { id: 2, title: '你常覺得身體上體力透支嗎?' },
          { id: 3, title: '你常覺得情緒上心力交瘁嗎?' },
          { id: 4, title: '你常會覺得，「我快要撐不下去了」嗎?' },
          { id: 5, title: '你常覺得精疲力竭嗎?' },
          { id: 6, title: '你常常覺得虛弱，好像快要生病了嗎?' },
        ],
        work: [
          { id: 1, title: '你的工作會令人情緒上心力交瘁嗎?' },
          { id: 2, title: '你的工作會讓你覺得快要累垮了嗎?' },
          { id: 3, title: '你的工作會讓你覺得挫折嗎?' },
          { id: 4, title: '工作一整天之後，你覺得精疲力竭嗎?' },
          { id: 5, title: '上班之前只要想到又要工作一整天，你就覺得沒力嗎?' },
          { id: 6, title: '上班時你會覺得每一刻都很難熬嗎?' },
          { id: 7, title: '不工作的時候，你有足夠的精力陪朋友或家人嗎?' },
        ]
      };
    }
  };
  </script>