<template>
  <div></div>
</template>
<script>
export default {
  components: {},
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
      required: false,
      type: Object,
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
      is_available: false,
      check_item: [1, 2, 3, 4, 5],
      car_arrays: [
        {
          id: 1,
          name: "toyota",
        },
        {
          id: 2,
          name: "Honda",
        },
        {
          id: 3,
          name: "Mitsubishi",
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
    is_available(oldValue, newValue) {
      console.log(oldValue);
      console.log(newValue);
    },
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