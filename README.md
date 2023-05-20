# Xray - Compatible_Five_Environments-Keeplive

为容器平台而生---此项目兼容GO、Python、Docker、VPS、Node五种环境+保活

***

## 项目说明
*  项目核心脚本和JS脚本来源于"Argo-Xray-JS-PaaS"，再次基础上做了保活加添
* 项目思路来源于“Argo-Xray-JS-PaaS”和“Argo-X-Container-PaaS”这两个脚本

## 思路阐述：
* 以entrypoint.sh为核心脚本，其他环境脚本都作为运行此脚本的启动器，故而使得多环境兼容并存。

## 注意事项
* 此项目虽说是兼容多环境，但由于测试平台有限（render平台为主）。有可能会出现平台不一样运行的机制会有所改变，导致无法部署！这也是实在没法避免的。不过关于多环境的脚本核心启动运行的部分已经写好，项目已经最大程度的把相关的依赖库都已经弄好，以保证在各个平台正常运行。如果不能正常运行可能就是平台的启动方式，需要自己阅读相关的官方文档进行调试，无须改动环境启动器的脚本。


### PaaS 平台用到的变量:

* PaaS 平台设置的环境变量
  | 变量名        | 是否必须 | 默认值 | 备注 |
  | ------------ | ------ | ------ | ------ |
  | UUID         | 否 | de04add9-5c68-8bab-950c-08cd5320df18 | 可在线生成 https://www.uuidgenerator.net/ |
  | ARGO_AUTH    | 否 |        | Argo 的 Token 或者 json 值 |
  | ARGO_DOMAIN  | 否 |        | Argo 的域名，须与 ARGO_DOMAIN 必需一起填了才能生效 |
  | WEB_USERNAME | 否 | admin  | 网页的用户名 |
  | WEB_PASSWORD | 否 | password | 网页的密码 |

* 路径（path）
  | 命令 | 说明 |
  | ---- |------ |
  | <URL>/list | 查看节点数据 |

## 自动部署
* GitHub  Action自动部署fly.io，使得fly平台部署更加简单方便。（支持“Argo-X-Container-PaaS”项目）


