<template>
  <ckeditor
    :editor="editor"
    :value="value"
    :config="config"
    :tagName="tagName"
    :disabled="disabled"
    @input="(event) => $emit('input', event)"
    @ready="(event) => $emit('ready', event)"
    @focus="(event) => $emit('focus', event)"
    @blur="(event) => $emit('blur', event)"
    @destroy="(event) => $emit('destroy', event)"
  />
</template>
<script>
import FullFreeBuildEditor from '@mikaleb/ckeditor5-build-classic'
import CKEditor from '@ckeditor/ckeditor5-vue2'

export default {
  components: {
    ckeditor: CKEditor.component,
  },

  props: {
    value: {
      type: String,
      required: false,
    },
    tagName: {
      type: String,
      required: false,
      default: 'div',
    },
    disabled: {
      type: Boolean,
      required: false,
    },
    uploadUrl: {
      type: String,
      required: false,
    },
    config: {
      type: Object,
      required: false,
      default: function () {},
    },
  },
  data() {
    return {
      editor: FullFreeBuildEditor,
    }
  },
}
</script>
