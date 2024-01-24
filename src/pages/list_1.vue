<template>
  <Layout title="肌肉骨骼症狀調查表">
    <template #content>
      <div class="flex flex-col space-y-8">
        <!-- 問題 -->
        <div>
          <Question v-for="(item, index) in question" :key="index"
            :showCheckButton:="true"
            :title="item.title"
            :id="item.id" 
            >
            <template #other>
              <div class="grid grid-cols-3 gap-4 mt-2 md:grid-cols-4 lg:grid-cols-6">
                <CheckButton v-for="(label, labelIndex) in checkbox[index]" :key="labelIndex" :label="label" class="flex flex-wrap " />
              </div>
            </template>
          </Question>
        </div>

        <!-- 說明 -->
        <div class="flex flex-col items-start p-4 bg-gray-100 lg:flex-row md:px-8 rounded-xl">
          <h3 class="mb-2 mr-4 md:text-lg">填寫說明</h3>
          <div class="flex flex-col">
            <p 
            v-for="(item, index) in info" :key="index"
            class="mb-2 md:text-lg"
            >
            {{ item.id }}，
            <span class="font-light">
              {{ item.label }}
            </span>
          </p>
          </div>
        </div>

        <!-- 症狀圖表 -->
        <div>
          <img src="" alt="">
          <Table :columns="columns" :data="data" />
        </div>

        <Confirm />

      </div>
    </template>
  </Layout>
</template>

<script>
export default {
  data() {
    return {
      question: [
        { 
          id: 1, 
          title: '您平常使用電腦、滑鼠慣用手為?', 
        },
        { 
          id: 2, 
          title: '您在過去的 1 年內，身體是否有長達 2 星期以上的疲勞、酸痛、發麻、刺痛等不舒服，或關節活動受到 限制?',
         },
        { 
          id: 3, 
          title: '下表的身體部位酸痛、不適或影響關節活動之情形持續多久時間?',
         },
      ],
      checkbox: [
        { 
          label1: '左手', 
          label2: '左手' 
        },
        { 
          label1: '否',
          label2: '是',
         },
        { 
          label1: '1 個月',
          label2: '3 個月',
          label3: '6 個月',
          label4: '1 年',
          label5: '3 年',
          label6: '3 年以上',
         },
      ],
      info: [
        { 
          id: '0 : 不痛', 
          label: '關節可以自由活動' 
        },
        { 
          id: '1 : 微痛', 
          label: '關節活動到極限會酸痛，可以忽略' 
        },
        { 
          id: '2 : 中等疼痛', 
          label: '關節活動超過一半會酸痛，但是可以完成全部活動範圍，可能影響工作' 
        },
        { 
          id: '3 : 劇痛', 
          label: '關節活動只有正常人的一半，會影響工作' 
        },
        { 
          id: '4 : 非常劇痛', 
          label: '關節活動只有正常人的 1/4，影響自主活動能力' 
        },
        { 
          id: '5 : 極度劇痛', 
          label: '身體完全無法自主活動。' 
        },
      ],
    };
  }
};
</script>