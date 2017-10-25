## 题目：使用nodeJs框架实现一个API接口
### 1）任意nodeJs框架都可以，例如experss、koa等，我公司目前使用koa
### 2）使用以上四个模块权限的数据（BASE、USER、CONNECTION、INVENTORY），实现一个API

### 3）监听端口3000，路由为/permissions
### 4）API要求根据请求接口参数返回不同模块的权限。返回数据格式如下
### 5）注册github账号，把代码上传到github，发送github项目连接并将成品图截图发送到hr@redshift.cc 注意代码、命名规范

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
### 需要数据


```
const permissionJson = {
    "BASE": {
      "PERMISSIONS": [
        "READ_INVENTORY_DASHBOARD",
        "READ_CONNECTION_DASHBOARD",
        "READ_USER_DASHBOARD",
        "READ_USER_EFFICIENCY_DASHBOARD",
        "READ_COMPANY_PROFILE",
        "UPDATE_COMPANY_PROFILE",
        "READ_BANK",
        "EDIT_BANK",
        "READ_ADDRESS",
        "EDIT_ADDRESS",
        "COMPLETE_DELETE",
        "READ_GLOBAL_HISTORY"
      ]
    },
    "USER": {
      "PERMISSIONS": [
        "MANAGE_DEPARTMENT",
        "MANAGE_USER",
        "MANAGE_ROLE",
        "ADD_ADMIN",
        "ADD_SUPERVISOR",
        "MANAGE_PROCESS"
      ]
    },
    "CONNECTION": {
      "PERMISSIONS": [
        "READ_CONNECTION",
        "EXPORT_CONNECTION",
        "IMPORT_CONNECTION",
        "MANAGE_CONNECTION",
        "MANAGE_CONNECTION_EP",
        "ALLOW_CONNECTION"
      ]
    },
    "INVENTORY": {
      "PERMISSIONS": [
        "READ_INVENTORY",
        "MANAGE_INVENTORY",
        "READ_INVENTORY_HISTORY",
        "READ_INVENTORY_LATEST_PRICE",
        "MANAGE_INVENTORY_CATEGORY",
        "ADOPT_INVENTORY"
      ]
    }
  }
}
```

```
const permissionMap = {
  "READ_INVENTORY_DASHBOARD": "商品统计查看",
  "READ_CONNECTION_DASHBOARD": "供应商统计查看",
  "READ_USER_DASHBOARD": "员工工作统计查看",
  "READ_USER_EFFICIENCY_DASHBOARD": "查看员工采购效率统计",
  "READ_COMPANY_PROFILE": "公司信息查看（包含联系人）",
  "UPDATE_COMPANY_PROFILE": "公司信息编辑（包含联系人）",
  "READ_BANK": "银行、发票信息查看",
  "EDIT_BANK": "银行、发票信息编辑",
  "READ_ADDRESS": "收货地址查看",
  "EDIT_ADDRESS": "收货地址管理",
  "COMPLETE_DELETE": "彻底删除权限",
  "READ_GLOBAL_HISTORY": "操作记录查看权限",
  "MANAGE_DEPARTMENT": "部门管理",
  "MANAGE_USER": "员工管理",
  "MANAGE_ROLE": "职位管理",
  "ADD_ADMIN": "添加管理员",
  "ADD_SUPERVISOR": "添加主管",
  "MANAGE_PROCESS": "流程管理",
  "READ_CONNECTION": "供应商查看",
  "EXPORT_CONNECTION": "供应商导出",
  "MANAGE_CONNECTION": "供应商管理(包括新建、修改、删除、禁用）",
  "MANAGE_CONNECTION_EP": "供应商灵活账期管理（包括开启/关闭、设置年化利率）",
  "IMPORT_CONNECTION": "供应商导入",
  "ALLOW_CONNECTION": "供应商准入",
  "READ_INVENTORY": "商品查看（第一个tab）",
  "MANAGE_INVENTORY": "商品管理（包括新增、修改、删除）",
  "READ_INVENTORY_HISTORY": "商品历史记录查看",
  "READ_INVENTORY_LATEST_PRICE": "禁止看商品历史成交价",
  "MANAGE_INVENTORY_CATEGORY": "商品类别管理",
  "ADOPT_INVENTORY": "商品采用"
}
```

```
const permissionTypeMap = {
    "BASE": "基础模块",
    "USER": "员工权限管理",
    "CONNECTION": "供应商管理",
    "INVENTORY": "商品管理"  }
```

