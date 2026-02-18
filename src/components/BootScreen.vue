<template>
    <div class="boot">
        <pre class="pre">{{ text }}<span v-if="inputActive && cursorOn" class="cursor"> </span></pre>
    </div>
</template>

<script setup lang="ts">
import { computed, onBeforeUnmount, onMounted, ref } from "vue";

const props = defineProps<{ userId?: string }>();
const emit = defineEmits<{ (e: "done"): void }>();

const prompt = "PS C:\\> ";
const lines = ref<string[]>([
    "Microsoft Windows [版本 10.0.22631.3085]",
    "(c) Microsoft Corporation. 保留所有权利。",
    "",
    prompt,
]);
const typed = ref("");
const cursorOn = ref(true);

let cursorTimer: number | undefined;
let dotTimer: number | undefined;

const inputActive = ref(true);

const text = computed(() => {
    const arr = [...lines.value];
    if (inputActive.value) {
        arr[arr.length - 1] = prompt + typed.value;
    }
    return arr.join("\n");
});
function sleep(ms: number) {
    return new Promise<void>((r) => window.setTimeout(r, ms));
}

async function typeText(s: string, speed = 60) {
    typed.value = "";
    for (const ch of s) {
        typed.value += ch;
        await sleep(speed);
    }
}

async function run() {
    await sleep(180);
    const bootText = props.userId ? `HAPPY NEW YEAR -id=${props.userId}` : "HAPPY NEW YEAR";
    await typeText(bootText, 55);
    await sleep(120);

    // 固化命令行（回车）
    lines.value[lines.value.length - 1] = prompt + typed.value;
    typed.value = "";
    inputActive.value = false; // 关键：后面不再强行覆盖最后一行

    lines.value.push("");
    lines.value.push("正在计算");

    // 点点动画：更新最后一行（不会再被 prompt 覆盖）
    let dots = 0;
    dotTimer = window.setInterval(() => {
        dots = (dots + 1) % 4;
        lines.value[lines.value.length - 1] = "正在计算" + ".".repeat(dots);
    }, 260);

    await sleep(3000);

    if (dotTimer) window.clearInterval(dotTimer);
    dotTimer = undefined;

    emit("done");
}

onMounted(() => {
    cursorTimer = window.setInterval(() => (cursorOn.value = !cursorOn.value), 520);
    run();
});

onBeforeUnmount(() => {
    if (cursorTimer) window.clearInterval(cursorTimer);
    if (dotTimer) window.clearInterval(dotTimer);
});
</script>

<style scoped>
.boot {
    height: 100%;
    background: #0b0b0b;
    padding: 14px 16px;
}

.pre {
    margin: 0;
    color: #d7d7d7;
    font-size: 14px;
    line-height: 1.65;
    white-space: pre-wrap;
    font-family: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace;
}

.cursor {
    display: inline-block;
    width: 8px;
    height: 16px;
    background: #d7d7d7;
    vertical-align: -2px;
}
</style>
