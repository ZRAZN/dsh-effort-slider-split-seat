# NOTICE

## 上游作品

本仓库基于以下作品修改：

- 名称：`@txc2768651338/dsh-effort-slider`
- 版本：`0.5.0`
- 维护者：`2768651338`
- 上游地址：<https://github.com/2768651338/dsh-effort-slider>
- 许可：BSD-3-Clause

上游 `LICENSE` 原文完整保留在本仓库的 [LICENSE](./LICENSE) 中，其中的版权声明（`Copyright (c) 2026, dsh-web-ui-custom contributors` 与 `Copyright (c) 2026, dsh-effort-slider contributors (standalone extraction)`）继续适用。

## 本修改版

- 名称：`dsh-effort-slider-split-seat`
- 版本：`0.6.0`
- 许可：BSD-3-Clause

相对上游 0.5.0 的修改：

1. **加载标识修正**：上游发布包在 `cordis.patch.yml` 与 `lib/client.js` 中使用了不带作用域的 `dsh-effort-slider`，当前 DSH 无法解析该包名。本版改为本仓库的包名与对应的客户端模块 id。
2. **模型座位拆分**：接管 `conversation.input.model` 座位，把原来的「模型 / 推理等级」两级菜单改为两个独立按钮——模型按钮直接展开模型列表，档位按钮直接展开 Effort 面板。
3. **新增模型列表弹层**：复用上游的会话目录快照（`directory.store`）与 `directory.select()`，按提供商分组渲染，当前项高亮。
4. **保留上游其余行为**：WebGL 火焰、拖动/吸附、档位别名与降级、宿主端思考强度供给、设置页开关等均未改动。

## 免责声明

本修改版由第三方维护，与上游作者无关。按 BSD-3-Clause 以 **“AS IS”** 基础提供，不附带任何明示或暗示的担保；使用风险自负。
