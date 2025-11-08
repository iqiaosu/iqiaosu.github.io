---
title: "SKILL SETS"
permalink: /about/skill-sets/
---

<div class="pdf-embed">
  <!-- 只预览，不提供下载链接 -->
  <object data="/assets/pdfs/skillsets.pdf" type="application/pdf" aria-label="Skill Sets PDF"></object>
  <div class="pdf-fallback" aria-hidden="true">
    PDF preview is not supported on this device/browser.
  </div>
</div>

<style>
/* 自适应预览容器（16:9，可按需改成 4/3、1/√2 等） */
.pdf-embed {
  position: relative;
  width: 100%;
  max-width: 1100px;        /* 视口最大宽度，可按需调整 */
  margin: 0 auto 1.25rem;   /* 居中 + 底部间距 */
  aspect-ratio: 16 / 9;     /* 关键：响应式高度 */
  background: #f6f7f9;
  border: 1px solid rgba(0,0,0,.06);
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 6px 24px rgba(0,0,0,.06);
}

.pdf-embed object {
  position: absolute;
  inset: 0;
  width: 100%;
  height: 100%;
  border: 0;
}

/* 如果浏览器不支持内嵌 PDF，显示简洁占位 */
.pdf-fallback {
  position: absolute;
  inset: 0;
  display: grid;
  place-items: center;
  color: #666;
  font-size: .95rem;
  padding: 1rem;
}

/* 小屏优化：在手机上改成更高的纵横比，阅读更舒服 */
@media (max-width: 640px) {
  .pdf-embed { aspect-ratio: 3 / 4; }
}
</style>
