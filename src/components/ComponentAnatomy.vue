<template>
  <div>
    <BaseLayout>
      <template v-slot:header>
        <!-- content for the header slot -->
      </template>
      <template v-slot:footer>
        <!-- content for the header slot -->
      </template>
      <!-- content for the default slot -->
    </BaseLayout>
  </div>
</template>
<script>
import ToDoItem from "./ToDoItem";
export default {
  components: {
    ToDoItem,
  },
  props: {
    title: {
      type: String,
      required: false,
    },
    array_items: {
      type: Array,
      required: false,
    },
    object_items: {
      required: true,
      type: Array | Object,
    },
    loading_boolean: {
      required: false,
      type: Boolean,
      default: false,
    },
    total: {
      required: false,
      type: Number,
      default: 0,
    },
  },
  data() {
    return {
      is_available: true,
      check_item: [1, 2, 3, 4, 5],
      car_array: [
        {
          id: 1,
          name: "toyota",
        },
        {
          id: 2,
          name: "Honda",
        },
      ],
    };
  },
  computed: {
    carAvailability() {
      return this.is_available ? "Yes" : "No";
    },
  },
  watch: {
    is_available(oldValue, newValue) {},
  },
  methods: {
    click() {
      console.log("click is working");
    },
  },
  beforeCreate() {},
  created() {},
  beforemount() {},
  mounted() {},
};
</script>