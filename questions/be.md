# 题目：后端面试题
## Step 1: 安装nodejs

安装后启动本地服务器。参考文档：https://nodejs.org/en/，
实现打开http://localhost:8080，
能返回基本Hello World页面

## Step 2：安装koa
安装后启动本地服务器。参考文档:http://koajs.com/，
实现打开http://localhost:8080，
能返回基本Hello World页面


## Step 3 实现一个函数 function mapPermissionName(permissions)
函数处理一个英文的权限结构，处理结果同时返回中英文对应的权限名称和权限类别名称。函数输入输出如下

### 输入数据

#### 1. 权限输入参数
```
{
    "DASHBOARD": {
      "PERMISSIONS": [
        "READ_INVENTORY_DASHBOARD",
        "READ_CONNECTION_DASHBOARD"
      ]
    },
    "USER": {
      "PERMISSIONS": [
        "MANAGE_DEPARTMENT",
        "MANAGE_USER"
      ]
    }
  }
}
```

#### 2.权限名称映射
```
const permissionMap = {
  "READ_INVENTORY_DASHBOARD": "商品统计查看",
  "READ_CONNECTION_DASHBOARD": "供应商统计查看",
  "MANAGE_DEPARTMENT": "部门管理",
  "MANAGE_USER": "员工管理"
}
```

#### 3.权限类别映射
```
const permissionTypeMap = {
    "DASHBOARD": "统计面板权限",
    "USER": "员工权限管理"}
```


### 输出结果
```
  {
    "DASHBOARD": {
      "name": "统计面板权限"
      "permissions": [
        {
          "type": "READ_INVENTORY_DASHBOARD",
          "name": "商品统计查看"
        },
        {
          "type": "READ_CONNECTION_DASHBOARD"
          "name": "供应商统计查看"
        },
      ]
    },
    "USER": {
      "name":  "员工权限管理"
      "permissions": [
        {
          "type": "MANAGE_DEPARTMENT",
          "name": "部门管理"
        },
        {
          "type": "MANAGE_USER",
          "name": "员工管理"
        },
      ]
    }
  }
```

## Step 4 实现接口
用curl请求http://localhost:3000/permission，成功返回上一步函数的处理结果

## Step 5 上传结果
注册github账号，把代码上传到github，发送github项目连接并将成品图截图发送到hr@redshift.cc 注意代码、命名规范



