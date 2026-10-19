# dsh-effort-slider-split-seat

把 DeepSeek Harness（DSH）输入框工具行里的模型座位，拆成两个独立按钮：

```
[ DeepSeek-V4.1-Flash ] │ [ High ]
```

- 点 **模型名** → 直接展开模型列表（按提供商分组，当前项高亮）；
- 点 **推理等级** → 直接展开 Claude 风格的 Effort 面板（无极拖动、松手吸附、WebGL 火焰）。

不再需要先点开一个大按钮、再在「模型 / 推理等级」二级菜单里二选一。

> 本仓库是 [`@txc2768651338/dsh-effort-slider@0.5.0`](https://github.com/2768651338/dsh-effort-slider) 的修改版（fork），不是原作者的发布物。修改内容与版权声明见 [NOTICE.md](./NOTICE.md)。

## 功能

- **双按钮座位**：模型与推理等级各自独立，一步直达。
- **模型列表**：按提供商分组，当前模型高亮，点击即切换；切换时带上该模型的默认档位。
- **推理等级面板**：完整保留上游效果——无极拖动、松手吸附、`OFF / Low / Medium / High / Ultracode` 档位、WebGL 火焰跟随、档位配色。
- **宿主端思考强度供给**：保留上游为缺少 `reasoning` 元数据的模型注入档位的能力。

## 安装

本地目录安装（DSH 桌面版 / web profile 通用）：

```sh
dsh plugin --profile <profile> add /path/to/dsh-effort-slider-split-seat
```

安装后重启 DSH。

也可以在 DSH 的「设置 → 插件市场」里用本地目录方式安装。

### 依赖

`@deepseek-ai/schemastery` 与 `@deepseek-ai/cosmokit` 已列入 `dependencies`，由包管理器安装。

如果你用 **link（符号链接）** 方式安装、且包管理器没有为它安装依赖，请保证这两个包可被解析，否则宿主端会报：

```
Cannot find package '@deepseek-ai/schemastery'
```

## 兼容性

- 在 DSH `0.2.1-rc.2`（Windows 桌面版）上验证。
- 客户端依赖 `ctx.modelDirectories` 与 `ctx.sessions`；缺失时插件不激活。
- 火焰效果需要 WebGL2；不可用时退化为普通轨道。

## 已知限制

- 接管 `conversation.input.model` 座位后，官方模型名后的 `[1017]` 徽章（`conversation.input.model.label` 子槽位）不再渲染。
- 官方 `/model` 命令仍可用，与两个按钮共用同一份会话目录。

## 许可

BSD-3-Clause，见 [LICENSE](./LICENSE)。上游版权声明保留在 LICENSE 与 [NOTICE.md](./NOTICE.md)。
