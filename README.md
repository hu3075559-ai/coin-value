# coin-value

古钱币/纸币拍照估价服务（需求验证版），静态单页，Cloudflare Pages 托管：
https://coin-value.pages.dev

- `/` 单页：价值主张（报真实成交区间）＋怎么估（三要素）＋示例报告
  （1980 年 2 角 8002 真实规格示例）＋价格（单件 ¥9.9 / 3 件 ¥19.9，拟定）
  ＋提交表单＋合规边界＋FAQ。

## 口径（硬）

- 只估已退出流通的钱币、纸币；只做信息估价，**不收购、不撮合交易**；
  估价为参考区间、不构成交易承诺；不碰出土文物。
- 估价口径：只报区间、注明参考成交来源、值多少报多少，不看挂牌价。
- 交付：照片收齐后 24 小时内出估价（区间＋依据＋来源）；
  先发照片确认能估，再付款。

## Layout / publishing

只有 `public/` 发布：Pages 项目 destination_dir=public。内容正本即
`public/index.html`（单文件含样式与脚本），改完经 gh.py 推送，
Pages 自动部署。

提交落库走 leads-api（POST https://lunasign.me/api/leads，
site=coin-value，联系方式/套餐/描述写入 note 字段），与 sellerscript、
schengen-alert 等站同一服务。表单为"先留联系方式、后在聊天里发照片"
模式，站上不收照片文件。
