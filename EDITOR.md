# 场景与道具配置

## 地图编辑器

打开 `admin.html`（或 `index.html?admin=1`），进入后会自动开启地图编辑模式。完成布置后，“导出 JSON”生成 `init.json`（HTTP 部署使用），“导出 INIT JS”生成 `init-data.js`（直接双击页面时使用）。覆盖项目同名文件即可发布新的初始地图。

浏览器已有存档不会被初始文件覆盖；验收初始地图时需清除站点的 `frog-game-v3` localStorage。

## 扩展道具

道具定义维护在 `object-catalog.json`，浏览器直接加载其离线兼容副本 `object-catalog.js`。追加道具时在两者的 `items` / 数组中追加同一对象，不需要修改 `game.js`。

- `id`：稳定且唯一的英文标识。
- `image`：相对 `sprites/cat-scholar/` 的完整路径，如 `object/home/tea_table_set.webp`。
- `assetGroup`：与目录一致；`object` 为玩家可摆，`map` 仅管理员可摆。
- `scene`：与子目录一致，只能是 `home` 或 `garden`。
- `tags`：用于分类、检索和后续玩法扩展。
- `layerTag`：`-1` 特殊底层，`1` 后景，`2` 自动深度，`3` 强制前景。
- `depthAnchorY`：自动深度层的落地点，`0` 为图片顶部、`1` 为底部。图片透明留白较多时，应把它调到实际接地位置；默认值为 `0.88`。

## 遮挡规则

人物、猫草鱼和 `layerTag: 2` 的物件位于同一深度空间，默认按实际落地点排序：猫取脚底、猫草鱼取根部，道具取 `depthAnchorY`。图片矩形的透明部分不会再直接决定层级。

编辑器的“后景 / 自动层 / 前景”用于处理墙面挂件、地毯、树冠等例外。数据还支持可选数字 `order`；存在时会覆盖自动 Y 排序，适合必须固定顺序的特殊对象。

## 目录约定

- `foods/`：食物与资源图片，永远不可布置。
- `map/home/`、`map/garden/`：初始地图素材，只有地图编辑器可以放置和修改。
- `object/home/`、`object/garden/`：玩家道具，只能在对应场景放置。

目录名、目录字段和场景校验必须保持一致。HOME/GARDEN 在代码和配置中统一使用小写 `home` / `garden`。
