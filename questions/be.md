## 题目：使用nodeJs框架实现一个API接口
### 1）任意nodeJs框架都可以，例如experss、koa等，我公司目前使用koa
### 2）使用以文档最后提供的数据实现返回权限名称中文映射结构，并完成一个API， 输入输出参数文档最后展示
### 3）要求监听端口3000，路由为/permissions
### 4）注册github账号，把代码上传到github，发送github项目连接并将成品图截图发送到hr@redshift.cc 注意代码、命名规范

### 输出结果
```
  {
    "status": 200,
    "data": {
      "BASE": {
        "name": {
          "chi": "基础模块"
        }
        "permissions": [
          {
            "type": "READ_INVENTORY_DASHBOARD",
            "name": {
                "chi": "商品统计查看"
            }
          },
          {
            "type": "READ_CONNECTION_DASHBOARD",
            "name": {
                "chi": "供应商统计查看"
            }
          },
        ]
      },
      "USER": {
        "name": {
          "chi": "员工权限管理"
        },
        "permissions": [
          {
            "type": "MANAGE_DEPARTMENT",
            "name": {
                "chi": "部门管理"
            }
          },
          {
            "type": "MANAGE_USER",
            "name": {
                "chi": "员工管理"
            }
          },
        ]
      }
    } 
  }
```
### 输入数据

### 1. 权限数据
```
const permissionJson = {
    "BASE": {
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

### 2.权限名称映射
```
const permissionMap = {
  "READ_INVENTORY_DASHBOARD": "商品统计查看",
  "READ_CONNECTION_DASHBOARD": "供应商统计查看",
  "MANAGE_DEPARTMENT": "部门管理",
  "MANAGE_USER": "员工管理",
  "MANAGE_ROLE": "职位管理"
}
```

### 3.权限类别映射映射
```
const permissionTypeMap = {
    "BASE": "基础模块",
    "USER": "员工权限管理"}
```

