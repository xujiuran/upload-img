### el-form

```
// 校验轮训分配配置
  private handleConfigvalidate(rule: any, value:any, callback: any) {
    if (!value) {
      return callback(new Error('请填写轮训分配设置'))
    } else {
      if (value < 30) {
        callback(new Error('不可少于30分钟'))
      } else {
        callback()
      }
    }
  }
```

el-form的自定义校验时，在校验成功是需手动callback()  否则校验成功会搜到阻碍导致

```
private handleCreateAllocation() {
    this.allocationFormVm.validate((valid: boolean) => {
      console.log(valid)
      console.log(this.allocationForm, 'form-----')
    })
  }
```

上述的 **validate** 方法的校验不通过，导致校验成功后无法触发成功