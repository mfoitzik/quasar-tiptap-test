<template>
  <q-page>
    <h1>Editor Content</h1>
    <p><a href="/">&lt;-Back</a></p>
    <div>
      <q-btn @click="showContent">Show Content in Console</q-btn>
    </div>
    <editor-content id="testid" :editor="editor" />
  </q-page>
</template>

<script>
import { Editor, EditorContent } from '@tiptap/vue-3'
import StarterKit from '@tiptap/starter-kit'
export default {
  name: 'EditorContentTest',
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
      //const el = document.getElementById('testid');
      console.log(this.editor.getHTML());
    }
  },
  mounted() {
    this.editor = new Editor({
      content: '<p>I’m running tiptap with Vue.js. 🎉</p>',
      extensions: [
        StarterKit,
      ],
    })
  },

  // beforeUnmount() {
  //   this.editor.destroy()
  // },
}
</script>
