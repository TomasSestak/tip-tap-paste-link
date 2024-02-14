<script setup lang="ts">
import Image from '@tiptap/extension-image';
import Link from '@tiptap/extension-link';
import {Placeholder} from '@tiptap/extension-placeholder';
import Underline from '@tiptap/extension-underline';
import StarterKit from '@tiptap/starter-kit';
import {type EditorOptions, useEditor} from '@tiptap/vue-3';
import Table from '@tiptap/extension-table';
import TableCell from '@tiptap/extension-table-cell';
import TableHeader from '@tiptap/extension-table-header';
import TableRow from '@tiptap/extension-table-row';
import {type ChainedCommands, Editor, EditorContent } from '@tiptap/vue-3';

const content = ref("adjsajdka jdk dak as")

const editorContent = useEditor({
  content: content.value,

  extensions: [
    StarterKit,
    Link.configure({
      openOnClick: false,
      linkOnPaste: false,
      autolink: false,
      HTMLAttributes: {
        class: 'editor-link',
      },
    }),
  ],
});
</script>

<template>
  <div class="h-screen w-screen flex justify-center items-center bg-slate-200">
    <EditorContent :editor="editorContent" class="text-green-800 bg-red-400 min-w-[400px] min-h-[400px] p-[30px]"/>
  </div>
</template>
