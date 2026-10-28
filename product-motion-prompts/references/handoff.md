# 从动画交接到网页

交付视频文件/帧序列、海报图、实际规格、每章起止位置、主体留白与网页文案。生成平台的临时链接可能失效；能下载时交付本地相对路径，无法下载则说明。

下面是有效JSON示例，example=true且所有媒体规格为null，不能当作真实已生成资产。实际交付时读取媒体元数据、确认对应文件后改为example=false。检查状态只记录实际完成的观察。

~~~json
{
  "version": 1,
  "example": true,
  "product": {
    "name": "橙色跑鞋",
    "palette": ["#FF692B", "#171717", "#F1EFE7"],
    "copy_space": "left",
    "mobile_subject_focus": "center-right"
  },
  "assets": [
    {
      "id": "main",
      "path": "assets/product-main.mp4",
      "poster": "assets/product-poster.webp",
      "width": null,
      "height": null,
      "fps": null,
      "duration_seconds": null,
      "inspection_status": "not_checked"
    }
  ],
  "chapters": [
    {"id": "arrival", "asset_id": "main", "range_normalized": [0, 0.1], "purpose": "完整产品入场"},
    {"id": "structure", "asset_id": "main", "range_normalized": [0.1, 0.6], "purpose": "展开并观察层次"},
    {"id": "return", "asset_id": "main", "range_normalized": [0.6, 1], "purpose": "归位后交给产品介绍"}
  ],
  "missing_assets": ["实际视频与海报", "不同配色素材"],
  "notes": "章节比例是示例规划，须按实际视频中的动作重新标定。"
}
~~~

网页阶段先读取实际时长再把比例换算成秒数。多个视频逐一列出资产和章节；不要用一个跨文件秒数混淆素材。缺少的配色、口味和细节图保持在missing_assets中，不能在网页上假装已具备。
