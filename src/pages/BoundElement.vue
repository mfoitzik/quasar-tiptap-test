<template>
  <q-page>
    <h1>bound element</h1>
    <p><a href="/">&lt;-Back</a></p>
    <div id="boundElement"></div>
    </q-page>
</template>

<script>
import { Editor, EditorContent } from '@tiptap/vue-3'
import StarterKit from '@tiptap/starter-kit'

export default {
  name: 'BoundElementTest',
  components: {
    EditorContent,
  },

  data() {
    return {
      editor: null,
    }
  },
  methods:  {
    showContent() {
      console.log(this.editor.getHTML());
    }
  },
  mounted() {
    this.editor = new Editor({
      element: document.getElementById('boundElement'),
      content: '<p>I’m running tiptap with Vue.js. 🎉</p>',
      extensions: [
        StarterKit,
      ],
    })
  },

  beforeUnmount() {
    this.editor.destroy()
  },
}
</script>
