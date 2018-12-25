# vue-upload
基于vue的上传组件

## 功能
- 单文件/多文件选择
- 大文件分片上传-合并校验
- 上传选择的文件限制-基于input[type="file"] accept
- 图片预览 `blob`

## 未完成
- 上传生命周期钩子
- 文件列表slot
- 开始上传slot
- doUpload手动触发上传
- autoUpload

## 依赖
- vue 2.0+
- axios 0.18+

## slot
- btn // 自定义上传按钮

## 参数
```
  props: {
    // 是否可多选
    multiple: {
      type: Boolean,
      default: true
    },
    // 等同input[type="file"] accept
    accept: {
      type: String,
      default: 'image/*'
    },
    // 上传的文件列表，可支持默认，必须设置preview属性和status=UPLOAD_SUCCESS
    fileList: {
      type: Array,
      default: () => [] 
    },
    // 上传最大文件限制
    maxSize: {
      type: Number,
      default: 5 * 1024 * 1024 * 1024
    },
    // 大于这个大小的文件使用分块上传(后端可以支持断点续传)
    multiUploadSize: {
      type: Number,
      default: 100 * 1024 * 1024
    },
    // 每块文件大小
    eachSize: {
      type: Number,
      default: 50 * 1024 * 1024
    },
    // 提交的文件地址
    postUrl: {
      type: String,
      default: 'http://localhost:8888'
    },
    // 验证合并文件块地址
    validateUrl: {
      type: String,
      default: 'http://localhost:8888/validateFile'
    }
  }
  ```