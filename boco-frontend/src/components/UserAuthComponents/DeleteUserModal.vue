<template>
  <!-- Main modal for deleting a user -->
  <div
    v-if="visible"
    class="fixed grid place-items-center bg-gray-600 bg-opacity-50 top-0 left-0 right-0 z-50 w-full overflow-x-hidden overflow-y-auto inset-0 h-full"
  >
    <div class="relative w-full h-full max-w-2xl p-4 md:h-auto">
      <!-- Modal content -->
      <div class="relative bg-white rounded-lg shadow dark:bg-gray-700">
        <!-- Modal header -->
        <div
          class="flex items-start justify-between p-4 border-b rounded-t dark:border-gray-600"
        >
          <h3 class="text-xl font-semibold text-gray-900 dark:text-white">
            Er du helt sikker?
          </h3>
          <button
            @click="close()"
            class="text-gray-400 bg-transparent hover:bg-gray-200 hover:text-gray-900 rounded-lg text-sm p-1.5 ml-auto inline-flex items-center dark:hover:bg-gray-600 dark:hover:text-white"
          >
            <svg
              class="w-5 h-5"
              fill="currentColor"
              viewBox="0 0 20 20"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                fill-rule="evenodd"
                d="M4.293 4.293a1 1 0 011.414 0L10 8.586l4.293-4.293a1 1 0 111.414 1.414L11.414 10l4.293 4.293a1 1 0 01-1.414 1.414L10 11.414l-4.293 4.293a1 1 0 01-1.414-1.414L8.586 10 4.293 5.707a1 1 0 010-1.414z"
                clip-rule="evenodd"
              ></path>
            </svg>
          </button>
        </div>
        <!-- Modal body -->
        <div class="p-6 space-y-6">
          <div
            @click="deleteUser"
            class="flex justify-center text-xl text-error-dark cursor-pointer"
          >
            Slett bruker
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "DeleteUserModal",
  props: {
    visible: Boolean,
  },
  methods: {
    close() {
      this.$emit("close");
    },
    deleteUser() {
      this.$emit("deleteUser");
    },
  },
};
</script>
