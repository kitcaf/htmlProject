<script setup lang="ts">
import {
    Dialog,
    DialogDescription,
    DialogHeader,
    DialogScrollContent,
    DialogTitle,
    DialogFooter,
} from '@/components/ui/dialog'
// import { Button } from '@/components/ui/button'

const props = defineProps<{
    open: boolean
}>()

const emit = defineEmits<{
    'update:open': [value: boolean]
}>()

const handleClose = () => {
    emit('update:open', false)
}
</script>

<template>
    <Dialog :open="open" @update:open="handleClose">
        <DialogScrollContent class="sm:max-w-[425px]">
            <DialogHeader>
                <DialogTitle>切换至手机模式获取最佳体验</DialogTitle>
            </DialogHeader>
            <div class="grid gap-4 py-4">
                <p>
                    1. 按 F12 调出控制台
                </p>
                <p>
                    2. 按 Ctrl+Shift+M，或点击下面图标
                </p>
            </div>
            <img src="@/assets/Snipaste_2025-01-17_22-27-21.png" alt="titMod" class="w-full">
        </DialogScrollContent>
    </Dialog>
</template>

<style lang="scss"></style>
