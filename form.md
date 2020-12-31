[toc]
## 基础字段
### 标题
```
config = {
  type: 'title',
  required: false,
  icon: 'icon-l-title',
  name: '标题',
  optional: {}
}
```
### 单行文本
```
config = {
  type: 'textline',
  required: false,
  icon: 'icon-l-textline',
  name: '单行文本',
  optional: {
    placeholder: '请输入' + name
  }
}
```
### 多行文本
```
config = {
  type: 'textarea',
  required: false,
  icon: 'icon-l-textarea',
  name: '多行文本',
  optional: {
    placeholder: '请输入' + name
  }
}
```
### 富文本
```
config = {
  type: 'richtext',
  required: false,
  icon: 'icon-l-textarea',
  name: '富文本',
  optional: {
    canImportWord:true
  }
}
```
### 下拉选择
```
config = {
  type: 'select',
  required: false,
  icon: 'icon-l-keyword',
  name: '下拉选择',
  optional: {
    options: [],
    placeholder: '请选择' + name
  }
}
```
### 多项选择
```
config = {
  type: 'checkboxs',
  required: false,
  icon: 'icon-l-checkbox',
  name: '多项选择',
  optional: {
    choiceType: 'checkbox',
    options: ['选项1','选项2'],
    direction: 'horizontal'
  }
}
```
### 日期选择
```
config = {
  type: 'date',
  required: false,
  icon: 'icon-l-date',
  name: '日期选择',
  optional: {
    pickerType: 'date',
    placeholder: '请选择' + name
  }
}
```
### 上传附件
```
config = {
  type: 'fileupload',
  required: false,
  icon: 'icon-l-upload',
  name: '上传附件',
  optional: {
    allowLimit: false,
    typeOptions: [],
    placeholder: ''
  }
}
```
### 关键词
```
config = {
  type: 'keywords',
  required: false,
  icon: 'icon-l-keyword',
  name: '关键词',
  optional: {
    max: 3,
    buttonName: ''
  }
}
```
### 评分---（设计重复）
```
config = {
  type: 'rate',
  required: false,
  icon: 'icon-l-rate',
  name: '评分',
  optional: {
    showStar: false,
    max: 5,
    options: [],
    direction: 'horizontal'
  }
}
```
### 联动选择
```
 config = {
  type: 'cascader',
  required: false,
  icon: 'icon-l-checkbox',
  name: '联动选择',
  optional: {
    options: []
  }
}
```
-------------------------------
## 高级字段 (表格配置缺少灵活性)
![](./1608887224(1).jpg '示例')
### 表格
```
config = {
  type: 'table',
  required: false,
  icon: 'icon-l-table',
  name: '表格',
  optional: {},
  children: []
}
```
### 选人列表
```
config = {
  type: 'userTable',
  required: false,
  icon: 'icon-l-table',
  name: '选人列表',
  optional: {
    buttonName: '添加成员'
  },
  children: [
    {
      type: 'textline',
      name: '文本框',
      required: false,
      optional: {}
    }
  ]
}
```
### 学术活动 - 活动选择
```
config = {
  type: 'asmsActivity',
  required: false,
  icon: 'icon-l-table',
  name: '活动列表',
  optional: {
    buttonName: '添加活动'
  },
  content: []
}
```
### 学术活动 - 上传证书
```
config = {
  type: 'asmsSelect',
  required: false,
  icon: 'icon-l-upload',
  name: '证书',
  optional: {
    buttonName: '上传附件',
    selectName: '选择证书',
    placeholder: ''
  }
}
```
# 统一配置为
```
config = {
  type: string, // 字段类型
  name: string, // 字段名称
  icon: string, // 系统图标
  required: boolean, // 是否必填
  optional: object, // 简单字段配置
  children: Array, // 嵌套表单配置
  *options*: Array, // 复杂字段配置
  *placeholder*: string, // 占位提示语
  *maxLength*: Number // 输入限制字数
}
optional: {
  buttonName: '添加成员',
  selectName: '选择证书',
  showStar: false,
  max: 5,
  direction: 'horizontal',
  canImportWord:true,
  choiceType: 'checkbox',
  pickerType: 'date',
  allowLimit: false,
  typeOptions: []
}
```