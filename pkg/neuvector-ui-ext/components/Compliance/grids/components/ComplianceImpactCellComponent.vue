<script>
import { EOS_APARTMENT_FILLED, EOS_CHECK_BOX_BLANK_FILLED, EOS_STORAGE_FILLED, EOS_SYSTEM_IMAGE_FILLED } from 'eos-icons-vue3';

export default {
  components: {
    EOS_APARTMENT_FILLED,
    EOS_CHECK_BOX_BLANK_FILLED,
    EOS_STORAGE_FILLED,
    EOS_SYSTEM_IMAGE_FILLED,
  },
  computed: {
  },
  methods: {
    refresh(params) {
      this.params = params
    }
  }
};
</script>

<template>
    <div class="row" v-if="params.node.data">
        <span
            v-if="params.node.data.images && params.node.data.images.length > 0"
            class="impact-col p-0">
            <EOS_SYSTEM_IMAGE_FILLED size="base" class="size-base"></EOS_SYSTEM_IMAGE_FILLED>
            {{ params.node.data.images.length }}
        </span>
        <span
            v-if="params.node.data.workloads && params.node.data.workloads.length > 0"
            class="impact-col p-0">
            <EOS_CHECK_BOX_BLANK_FILLED size="base" class="size-base"></EOS_CHECK_BOX_BLANK_FILLED>
            {{ params.node.data.workloads.length }}
        </span>
        <span
            v-if="params.node.data.nodes && params.node.data.nodes.length > 0"
            class="impact-col p-0">
            <EOS_STORAGE_FILLED size="base" class="size-base"></EOS_STORAGE_FILLED>
            {{ params.node.data.nodes.length }}
        </span>
        <span
            v-if="params.node.data.platforms && params.node.data.platforms.length > 0"
            class="impact-col p-0">
            <EOS_APARTMENT_FILLED size="base" class="size-base"></EOS_APARTMENT_FILLED>
            {{ params.node.data.platforms.length }}
        </span>
    </div>
</template>

<style lang="scss" scoped>
@import '../../../../styles/neuvector.scss';
.impact-col {
  -webkit-box-flex: 0;
  -ms-flex: 0 0 25%;
  flex: 0 0 25%;
  max-width: 25%;
  display: flex;
  align-items: center;
}

.size-base {
  min-width: 14px;
}
</style>