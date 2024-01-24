<template>
  <Layout title="過勞量表">
    <template #content>
      <div class="flex flex-col space-y-8">
        <h2>
          親愛的同仁您好:
          <br/>
          此「過勞量表」是勞動部針對過勞壓力反應編製;可協助在短時間內瞭解工作壓力引起的過勞反 應或過勞傾向。對於您所提供的資料，將只用於公司醫務室健康管理分析使用，而且絕對保密，請 安心填寫，謝謝!
        </h2>
  
        <div class="w-full border-t border-gray-300" />
  
        <!-- 個人疲勞 -->
        <div>
          <h3 class="pl-4 mb-4 text-lg border-l-8 border-black md:text-2xl">個人疲勞</h3>
          <Question v-for="(item, index) in person" :key="index"
            :showLikertScale="true" 
            :title="item.title"
            :id="item.id" 
            />
        </div>

        <div class="w-full border-t border-gray-300" />

        <!-- 工作疲勞 -->
        <div>
          <h3 class="pl-4 mb-4 text-lg border-l-8 border-black md:text-2xl">工作疲勞</h3>
          <Question v-for="(item, index) in work" :key="index"
            :showLikertScale="true" 
            :title="item.title"
            :id="item.id" 
            />
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