<template>
    <div ref="viewport" class="tui">
        <!-- 设计画布：固定尺寸，用缩放适配窗口大小，保证布局比例稳定 -->
        <div class="stage" :class="{ mobile: isMobile }" :style="stageStyle">
            <div class="title-block">
                <div class="pixel-title">HAPPY CODE YEAR</div>
            </div>

            <div class="slogan">
                <span class="horse">🐴</span>
                <span class="slogan-text" v-if="!isMobile">码 年 大 吉 ・ 丙 午 年 ・ 万 码 奔 腾</span>
                <span class="slogan-text" v-else>码 年 大 吉<br>丙 午 年<br>万 码 奔 腾</span>
                <span class="horse">🐴</span>
            </div>

            <div class="intro">
                <div class="invader">
                    <InvaderIcon :size="70" />
                </div>
                <div class="intro-text">
                    <div>Welcome to 丙午马年 v2026.2.17</div>
                    <div>
                        cwd:
                        <span class="teal">~/2026/todo</span>
                    </div>
                    <div>
                        model:
                        <span class="teal">claude-opus-4.6</span>
                        <span class="muted">（码力全开版）</span>
                    </div>
                    <div>
                        Tip:
                        <span class="tip">新的一年多学习，也要多休息</span>
                    </div>
                </div>
            </div>

            <div class="panels">
                <!-- Plan -->
                <div class="panel">
                    <div class="panel-header">
                        <span class="panel-header-text">Plan</span>
                    </div>

                    <div class="panel-body">
                        <div class="panel-top">
                            <div>2026 年度愿望清单确认</div>
                            <div>请确认你的新年需求:</div>
                        </div>

                        <div class="section">
                            <div class="section-title">◆ 今年生活上要:</div>

                            <div class="row">
                                <span class="cb"></span><span class="cn">身体健康</span><span class="dash">—</span>
                                <span class="mono">uptime: 365d, 0 crashes, 0 hotfixes</span>
                            </div>
                            <div class="row">
                                <span class="cb"></span><span class="cn">财运亨通</span><span class="dash">—</span>
                                <span class="mono">bonus = int('overflow')</span>
                            </div>
                            <div class="row">
                                <span class="cb"></span><span class="cn">无忧无虑</span><span class="dash">—</span>
                                <span class="mono">rm -rf ~/anxiety ~/stress ~/self-doubt</span>
                            </div>
                            <div class="row">
                                <span class="cb"></span><span class="cn">达成目标</span><span class="dash">—</span>
                                <span class="mono">assert all(goal.done for goal in y2026)</span>
                            </div>
                        </div>

                        <div class="section">
                            <div class="section-title">◆ 今年学业上要:</div>

                            <div class="row">
                                <span class="cb"></span><span class="cn">一次上岸</span><span class="dash">—</span>
                                <span class="mono">offer = recruit.accept(top_choice)</span>
                            </div>
                            <div class="row">
                                <span class="cb"></span><span class="cn">连发Paper</span><span class="dash">—</span>
                                <span class="mono">papers.append(CCF_A)</span>
                            </div>
                            <div class="row">
                                <span class="cb"></span><span class="cn">每个idea都work</span><span class="dash">—</span>
                                <span class="mono">for idea in brain: pass</span>
                            </div>
                            <div class="row">
                                <span class="cb"></span><span class="cn">显卡自由</span><span class="dash">—</span>
                                <span class="mono">gpu_cluster = [H200] * 128</span>
                            </div>
                            <div class="row">
                                <span class="cb"></span><span class="cn">经费充足</span><span class="dash">—</span>
                                <span class="mono">grant.balance = Decimal('Infinity')</span>
                            </div>
                        </div>

                        <div class="section">
                            <div class="section-title">◆ 今年工作上要:</div>

                            <div class="row">
                                <span class="cb"></span><span class="cn">升职加薪</span><span class="dash">—</span>
                                <span class="mono">salary += salary * 0.5</span>
                            </div>
                            <div class="row">
                                <span class="cb"></span><span class="cn">需求不变更</span><span class="dash">—</span>
                                <span class="mono">git revert product_manager --hard</span>
                            </div>
                            <div class="row">
                                <span class="cb"></span><span class="cn">准时下班</span><span class="dash">—</span>
                                <span class="mono">crontab -e # 18:00 /usr/bin/go-home</span>
                            </div>
                            <div class="row">
                                <span class="cb"></span><span class="cn">Vibe Coding 一次过</span><span class="dash">—</span>
                                <span class="mono">cursor.run(prompt) == LGTM</span>
                            </div>
                            <div class="row">
                                <span class="cb"></span><span class="cn">配环境不报错</span><span class="dash">—</span>
                                <span class="mono">pip install . && exit 0 # 一次搞定</span>
                            </div>
                        </div>

                        <div class="divider"></div>

                        <div class="prompt">
                            <div><span class="gt">&gt;</span> 你的选择: <span class="pick">我全都要!</span></div>
                            <div><span class="ok">✓</span> 已确认，正在部署到 <span class="ok-strong">2026</span>...</div>
                        </div>
                    </div>
                </div>

                <!-- Execution -->
                <div class="panel">
                    <div class="panel-header">
                        <span class="panel-header-text">Execution</span>
                    </div>

                    <div class="panel-body">
                        <div class="mono block">
                            <div>diff --git a/2025.life b/2026.life</div>
                            <div>--- a/2025.life</div>
                            <div>+++ b/2026.life</div>
                            <div class="amber">@@ -1,8 +1,8 @@</div>
                        </div>

                        <div class="block">
                            <div class="chg minus">- 久坐不动，熬夜通宵</div>
                            <div class="chg plus">+ 规律作息，精力充沛</div>

                            <div class="chg minus">- 论文被拒，导师已读不回</div>
                            <div class="chg plus">+ 中奖顶会，导师疯狂点赞</div>

                            <div class="chg minus">- 配环境三天，跑代码三分钟</div>
                            <div class="chg plus">+ 一键部署，开箱即用</div>

                            <div class="chg minus">- 显卡排队，<span class="tok red">Token</span> 精尽</div>
                            <div class="chg plus">+ 算力无限，<span class="tok green">Token</span> 自由</div>

                            <div class="chg minus">- 需求变更，通宵加班</div>
                            <div class="chg plus">+ 准时下班，需求冻结</div>

                            <div class="chg minus">- 玄学 bug，重启也没用</div>
                            <div class="chg plus">+ 代码优雅，零 <span class="mono">warning</span></div>

                            <div class="chg minus">- 余额不足，花呗还款</div>
                            <div class="chg plus">+ 财务自由，被动收入</div>

                            <div class="chg minus">- 焦虑内耗，精神紧绷</div>
                            <div class="chg plus">+ 心态平和，快乐充实</div>
                        </div>

                        <div class="mono block">
                            <div class="amber">$ git add .</div>
                            <div class="amber">$ git commit -m "辞旧迎新 2026"</div>
                            <div>[main 2026] 辞旧迎新 2026</div>
                            <div>&nbsp;&nbsp;8 files changed, 8 insertions(+),</div>
                            <div>&nbsp;&nbsp;8 deletions(-)</div>
                            <div class="amber">$ git push origin main</div>
                            <div class="okline">✓ 已推送至 <span class="ok-strong">2026</span> 🐴</div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup lang="ts">
import { computed, onBeforeUnmount, onMounted, ref } from "vue";
import InvaderIcon from "./InvaderIcon.vue";

const DESIGN_W = 980;
const DESIGN_H = 720;

const viewport = ref<HTMLDivElement | null>(null);
const scale = ref(1);
const isMobile = ref(false);

let ro: ResizeObserver | undefined;

function updateMode() {
    isMobile.value = window.innerWidth < 1280; // 只分两档
}

function updateScale() {
    if (isMobile.value) {
        // 手机端不整体缩放，交给 CSS 做正常流式布局
        scale.value = 1;
        return;
    }
    const el = viewport.value;
    if (!el) return;
    const rect = el.getBoundingClientRect();
    const s = Math.min((rect.width * 0.96) / DESIGN_W, (rect.height * 0.96) / DESIGN_H);
    scale.value = Math.max(0.2, Math.min(2.2, s));
}

onMounted(() => {
    updateMode();
    updateScale();

    ro = new ResizeObserver(() => {
        updateMode();
        updateScale();
    });
    if (viewport.value) ro.observe(viewport.value);

    window.addEventListener("resize", () => {
        updateMode();
        updateScale();
    });
});

onBeforeUnmount(() => {
    ro?.disconnect();
    window.removeEventListener("resize", () => {
        updateMode();
        updateScale();
    });
});

const stageStyle = computed(() => {
    if (isMobile.value) return {}; // 关键：手机端不再写 transform/固定宽高内联样式
    return {
        width: `${DESIGN_W}px`,
        height: `${DESIGN_H}px`,
        transform: `translate(-50%, -50%) scale(${scale.value})`,
    };
});






</script>

<style scoped>
.tui {
    height: 100%;
    background: #dbd2c1;
    position: relative;
    overflow: hidden;
    font-family: "ZPIX", "FusionPixel", ui-monospace, Menlo, Consolas, monospace;
    color: #3d342b;
}

.stage {
    position: absolute;
    left: 50%;
    top: 50%;
    transform-origin: center;
}

/* 标题：用 text-shadow 堆出像素叠影感（字体是关键） */
.title-block {
    text-align: center;
    margin-top: 0px;
}

.pixel-title {
    font-family: "PIXEL_TITLE", "ZPIX", ui-monospace, monospace;
    font-weight: 900;
    letter-spacing: 10px;
    line-height: 0.88;
    font-size: 70px;
    color: #9b5b35;
    text-shadow:
        3px 0 0 #caa987,
        0 3px 0 #caa987,
        3px 3px 0 #caa987,
        6px 6px 0 #b88f6d,
        9px 9px 0 #a67c5b,
        12px 12px 0 #956e50;
}

.slogan {
    margin-top: 10px;
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 18px;
    color: #b88f6d;
    font-size: 14px;
}

.slogan-text {
    letter-spacing: 6px;
}

.horse {
    color: #2b241e;
    font-size: 14px;
}

.intro {
    margin-top: 8px;
    display: flex;
    align-items: flex-start;
    gap: 18px;
    padding: 0 46px;
}

.invader {
    width: 86px;
    display: grid;
    place-items: center;
}

.intro-text {
    font-size: 14px;
    line-height: 1.1;
}

.teal {
    color: #3b8d8c;
    font-weight: 700;
}

.muted {
    color: #6e6256;
}

.tip {
    color: #c59664;
    font-weight: 700;
}

/* Panels */
.panels {
    margin-top: 0px;
    padding: 0 34px;
    display: grid;
    grid-template-columns: 2fr 1fr;
    gap: 22px;
}

.panel {
    border: 2px solid #c4b39a;
    border-radius: 10px;
    background: rgba(255, 255, 255, 0.12);
    box-shadow: inset 0 0 0 2px rgba(255, 255, 255, 0.08);
    overflow: hidden;
}

.panel-header {
    position: relative;
    height: 36px;
    display: grid;
    place-items: center;
}

.panel-header::before {
    content: "";
    position: absolute;
    left: 18px;
    right: 18px;
    top: 18px;
    height: 2px;
    background: rgba(61, 52, 43, 0.35);
}

.panel-header-text {
    position: relative;
    padding: 0 12px;
    background: #dbd2c1;
    color: #c59664;
    font-size: 14px;
    font-weight: 900;
    letter-spacing: 2px;
}

.panel-body {
    padding: 0px 12px 10px 32px;
    font-size: 12px;
}

/* Plan 左侧排版 */
.panel-top {
    margin-bottom: 10px;
    font-size: 14px;
    line-height: 1;
}

.section {
    margin-top: 12px;
}

.section-title {
    color: #c59664;
    font-weight: 900;
    margin-bottom: 6px;
    font-size: 13px;
}

.row {
    display: grid;
    grid-template-columns: 24px 150px 26px 1fr;
    align-items: center;
    gap: 10px;
    padding: 1px 0;
}

.cb {
    width: 12px;
    height: 12px;
    background: #6b5bd3;
    border-radius: 3px;
    position: relative;
    box-shadow: inset 0 -2px 0 rgba(0, 0, 0, 0.18);
}

.cb::after {
    content: "";
    position: absolute;
    left: 3px;
    top: 1px;
    width: 3px;
    height: 6px;
    border-right: 2px solid #fff;
    border-bottom: 2px solid #fff;
    transform: rotate(38deg);
}

.cn {
    font-weight: 800;
}

.dash {
    color: rgba(61, 52, 43, 0.6);
    font-weight: 900;
}

.mono {
    font-family: ui-monospace, Menlo, Consolas, "Courier New", monospace;
    font-size: 12px;
    letter-spacing: 0.1px;
}

.divider {
    margin-top: 12px;
    height: 2px;
    background: rgba(61, 52, 43, 0.55);
}

.prompt {
    margin-top: 10px;
    line-height: 1.45;
}

.gt {
    color: #3d342b;
    font-weight: 900;
}

.pick {
    color: #c59664;
    font-weight: 900;
}

.ok {
    color: #2f8f4e;
    font-weight: 900;
}

.ok-strong {
    color: #1f7a3f;
    font-weight: 900;
}

/* Execution 右侧 */
.block {
    margin-top: 0px;
}

.amber {
    color: #c59664;
    font-weight: 900;
}

.chg {
    font-weight: 900;
    line-height: 1.38;
    margin: 2px 0;
}

.minus {
    color: #b04a46;
}

.plus {
    color: #2f8f4e;
}

.tok {
    font-weight: 900;
}

.tok.red {
    color: #b04a46;
}

.tok.green {
    color: #2f8f4e;
}

.okline {
    margin-top: 2px;
    color: #2f8f4e;
    font-weight: 900;
}
@media (max-width: 1279px) {
    .tui {
        overflow: auto;
        /* 手机要能上下滚，否则内容挤压 */
    }
    .slogan-text {
        margin-top: 20px;
    }
    .horse {
        margin-top: 20px;
    }
    .stage.mobile {
        position: relative;
        left: auto;
        top: auto;
        transform: none !important;
        width: 100%;
        height: auto;
        padding-top: 10px;
        padding-bottom: 10px;
    }

    /* 标题和顶部信息在手机上适当缩小字距、增大可读性 */
    .pixel-title {
        font-size: 44px;
        letter-spacing: 6px;
    }

    .intro {
        padding: 0 10px;
        gap: 12px;
    }

    .intro-text {
        font-size: 16px;
        line-height: 1.25;
    }

    /* 关键：Plan / Execution 改成上下排，且满宽 */
    .panels {
        grid-template-columns: 1fr;
        padding: 0 10px;
        gap: 14px;
        margin-top: 12px;
    }

    .panel-body {
        padding: 10px 12px 12px 12px;
        font-size: 14px;
    }

    /* 行内布局收窄，代码允许断行 */
    .row {
        grid-template-columns: 18px 96px 14px 1fr;
        gap: 8px;
        align-items: start;
    }

    .mono {
        font-size: 13px;
        overflow-wrap: anywhere;
        word-break: break-word;
    }
}

</style>