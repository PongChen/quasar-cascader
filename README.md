# Quasar App (quasar-cascader)

Base Quasar Framework app

## Install the dependencies
```bash
npm install
```

### Start the app in development mode (hot-code reloading, error reporting, etc.)
```bash
quasar dev
```
### Use as component in quasar
```
npm i quasar-cascader

import Cascader from "quasar-cascader"

<Cascader
  ref="wt"
  label="部门"
  :options="deptsOption"
  optlabel="name"
  optvalue="id"
  :selected="selected"
  @change="handleDeptIdChange"
></Cascader>
```
### props
```
    options:数据集合
    selected: 初始显示项
    label: 标题
    optvalue: 设置用于绑定的字段名称
    optlabel: 设置用于显示的字段名称
    dense: 大小-q-select
    important:必选
    readonly: 只读
```

### demo view
![GIF](https://user-images.githubusercontent.com/21305978/114809386-ab76fd00-9ddc-11eb-86fc-0bafc8e0a4d8.gif)

