---
title: 表组件
order: 0
---

## SpreadsheetProps

功能描述： 基于 core 层封装的 react 版开箱即用组件。

| 参数 | 说明                                                         | 类型 | 默认值  | 必选 |
| :--- | :--- | :--- | :--- | :---: |
| sheetType |  表格类型：<br> 1. `pivot`: 透视表 <br> 2. `table`: 明细表 <br> 3. `gridAnalysis`: 网格分析表| `pivot | table | gridAnalysis` | `pivot` | |
| spreadsheet | |`(...args: S2Constructor) => SpreadSheet`| |  |
| dataCfg |  透视表数据映射相关配置项 | [S2DataConfig](/zh/docs/api/general/S2DataConfig) | | ✓ |
| options | 透视表属性配置项 | [S2Options](/zh/docs/api/general/S2Options) | | ✓ |
| partDrillDown |  维度下钻相关属性 | [PartDrillDown](/zh/docs/api/components/drill-down) | |  |
| adaptive | 是否根据窗口大小自适应 | `boolean` | `false` | |
| showPagination | 是否显示默认分页<br>(只有在 `options` 配置过 Pagination  属性才会生效) | `boolean` | `true` | |
| themeCfg | 自定义透视表主题样式 | [ThemeCfg](/zh/docs/api/general/S2Theme) | |  |
| isLoading | 控制表格的加载状态 | `boolean` | | |
| header | 表头配置项 | [HeaderCfgProps](/zh/docs/api/components/header) | | |
| getSpreadSheet | 获取表实例 | (spreadsheet: SpreadSheet) => void; | | |
| onListSort | 排序回调，用于做自定义排序 |  (params: [ListSortParams](#listsortparams) ) => void; | |  |
| onRowCellClick| 行头单击回调事件| (data: [TargetCellInfo](#targetcellinfo)) => void | | |
| onRowCellDoubleClick| 行头双击回调事件| (data: [TargetCellInfo](#targetcellinfo)) => void | | |
| onColCellClick| 列头单击回调事件| (data: [TargetCellInfo](#targetcellinfo)) => void | | |
| onColCellDoubleClick| 列头双击回调事件| (data: [TargetCellInfo](#targetcellinfo)) => void | | |
| onCornerCellClick| 角头单击回调事件| (data: [TargetCellInfo](#targetcellinfo)) => void | | |
| onDataCellClick| | (data: [TargetCellInfo](#targetcellinfo)) => void | | |
| onDataCellDoubleClick| 交叉单元格双击回调事件| (data: [TargetCellInfo](#targetcellinfo)) => void | | |
| onMergedCellClick| | (data: [TargetCellInfo](#targetcellinfo)) => void | | |
| onMergedCellDoubleClick| 合并单元格双击回调事件| (data: [TargetCellInfo](#targetcellinfo)) => void | | |
| onContextMenu| 右键单元格单击回调事件| (data: [TargetCellInfo](#targetcellinfo)) => void | | |

### ListSortParams

<description> **required**  _object_ </description>

功能描述：排序回调函数的返回的信息。

| 参数 | 说明                      | 类型 | 默认值  | 必选 |
| :--- | :--- | :--- | :--- | :---: |
| sortFieldId | 当前排序的维度或度量的 id | `string` | | ✓ |
| sortMethod | 当前排序方式 | `string` | | ✓ |

### TargetCellInfo

<description> **required**  _object_ </description>

功能描述：交互回调函数的返回信息。

| 参数 | 说明                   | 类型 | 默认值  | 必选 |
| :--- | :--- | :--- | :--- | :---: |
| target | 交互作用对象 | `any` | | ✓ |
| event | 事件 | `Event` | | ✓ |
| viewMeta | 当前交互作用的结点信息 | `Node` | | ✓ |