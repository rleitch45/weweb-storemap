<template>
  <div style="padding: 20px">
    <svg
      viewBox="0 0 2000 1200"
      style="width: 100%; height: auto; background: #f5f5f5; border: 1px solid #ccc"
    >
      <rect
        v-for="shape in content.shapes"
        :key="shape.id"
        :x="shape.x"
        :y="shape.y"
        :width="shape.width"
        :height="shape.height"
        :fill="getColor(shape.status)"
        stroke="#000"
        stroke-width="1"
      />
    </svg>
  </div>
</template>

<script setup>
const props = defineProps({
  content: {
    type: Object,
    required: true
  }
})

const getColor = (status) => {
  switch (status) {
    case "W1 COMPLETE": return "#e920c0"
    case "W2 COMPLETE": return "#8b20e9"
    case "W3 COMPLETE": return "#203ce9"
    case "W4 COMPLETE": return "#20a5e9"
    case "W5 COMPLETE": return "#20e9c0"
    case "W6 COMPLETE": return "#20e98b"
    case "W7 COMPLETE": return "#4ee920"
    case "W8 COMPLETE": return "#d1e920"
    default: return "#cccccc"
  }
}
</script>