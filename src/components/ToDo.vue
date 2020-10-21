<template>
  <v-container>

    <!-- Список задач -->
    <v-card class="mb-5">
      <v-card-title>TODO</v-card-title>
      <v-card-text>

        <!-- Компоненты списка -->
        <v-list v-if="tasks.length">

          <v-list-item dense v-for="(task, i) in tasks" :key="i">
            <v-list-item-content>
              <v-list-item-title>
                {{ task.title }}
              </v-list-item-title>
              <v-list-item-subtitle>
                {{ task.text }}
              </v-list-item-subtitle>
            </v-list-item-content>

            <v-spacer/>

            <v-btn color="red" dark fab x-small icon @click="removeTask(i)">
              <v-icon>mdi-delete</v-icon>
            </v-btn>

          </v-list-item>

        </v-list>

        <!-- Если задач 0 -->
        <div v-else>
          Список пуст
        </div>

      </v-card-text>
    </v-card>

    <!-- Карточка добавления новой задачи -->
    <v-card>
      <v-card-text>
        <v-text-field v-model="title" dense outlined label="Task title"/>
        <v-text-field v-model="text" dense outlined label="Task description"/>
      </v-card-text>
      <v-card-actions>
        <v-spacer/>
        <v-btn color="primary" @click="addTask">
          <v-icon left>
            mdi-plus-circle
          </v-icon>
          Add
        </v-btn>
      </v-card-actions>
    </v-card>

  </v-container>
</template>

<script>
export default {
  data: () => ({
    tasks: [],
    title: '',
    text: '',
  }),

  methods: {
    addTask() {
      this.tasks.push({
        title: this.title,
        text: this.text,
      })
      this.title = ''
      this.text = ''
    },
    removeTask(i) {
      this.tasks.splice(i, 1)
    },
  },
}
</script>

<style scoped lang="sass">

</style>
