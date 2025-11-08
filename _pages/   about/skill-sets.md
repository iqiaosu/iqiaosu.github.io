---
title: "SKILL SETS"
permalink: /about/skill-sets/
---

<div class="pdf-embed">
  <!-- 方案 A：多数浏览器最稳 -->
  <iframe
    src="/assets/pdfs/skillsets.pdf#toolbar=0&navpanes=0&view=FitH"
    title="Skill Sets PDF"
    loading="lazy"
    referrerpolicy="no-referrer"
  ></iframe>

  <!-- 方案 B：如果 iframe 失败尝试 embed（部分 Safari/macOS 更喜欢这个） -->
  <embed
    src="/assets/pdfs/skillsets.pdf#view=FitH"
    type="application/pdf"
  />

  <!-- 方案 C：仍不支持时显示占位提示（不提供下载链接） -->
  <div class="pdf-fallback" aria-hidden="true">
    PDF preview is not supported on this device/browser.
  </div>
</div>

<style>
.pdf-embed{
  position:relative;
  width:100%;
  max-width:1100px;
  margin:0 auto 1.25rem;
  aspect-ratio:16/9;             /* 手机可读性：如需更高改成 3/4 */
  background:#f6f7f9;
  border:1px solid rgba(0,0,0,.06);
  border-radius:12px;
  overflow:hidden;
  box-shadow:0 6px 24px rgba(0,0,0,.06);
}
.pdf-embed iframe,
.pdf-embed embed{
  position:absolute;
  inset:0;
  width:100%;
  height:100%;
  border:0;
  display:block;
}
.pdf-fallback{
  position:absolute;
  inset:0;
  display:grid;
  place-items:center;
  color:#666;
  font-size:.95rem;
  padding:1rem;
}
/* 小屏更高一些，便于阅读 */
@media (max-width:640px){
  .pdf-embed{ aspect-ratio:3/4; }
}
</style>
