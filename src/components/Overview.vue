<template>
  <div class="text-blue-900">
    <div class="text-2xl font-bold">Answers Overview</div>

    <div class="my-4">Here you can see and change your answers</div>

    <Collapsible
      v-for="(group, index) of groupAnswers"
      :key="group.title"
      :title="group.title"
      :open="index === 0"
    >
      <div
        class="my-4"
        v-for="question of group.questions"
        :key="question.question"
      >
        <div class="font-bold">{{ question.question }}</div>
        <div class="my-2 text-gray-400">
          {{ question.answer }}
        </div>
      </div>
    </Collapsible>
  </div>
</template>

<script>
import Collapsible from "./controls/Collapsible.vue";

export default {
  props: ["groupAnswers"],

  components: {
    Collapsible,
  },
  data() {
    return {};
  },
  methods: {},
};
</script>