# Raspberry
# 树莓咖啡屋线上平台
## 需求分析与设计文档

## 项目概述

本项目旨在为"树莓"咖啡屋开发一个集线上点单和电商购物于一体的移动端优先独立站。该平台将支持店内餐饮点单（包括西餐、酒水饮品和私厨服务）以及古着、文艺饰品的境外销售，并通过TikTok引流提升曝光。

核心价值主张：在一个充满文艺复古艺术气息的空间里，发现独特古着并享受美食的治愈体验。

- 店主、平台管理员可以通过可视化数据看到收入数据的日、月、年变化和占比
- 通过TikTok引流获得新注册用户
- 支持手机端使用，提升用户体验
- 初期侧重服务到店的本地顾客提升点餐效率，后期实现境外古着电商销售

---

## 用户画像

| 用户类型 | 核心特征与需求 | 使用场景 | 业务价值 |
| --- | --- | --- | --- |
| 本地顾客-小杨（白领/社交达人） | 25岁，追求小众、文艺，注重体验与拍照分享，常消费饮品、甜点、古着浏览 | 周末与朋友小聚，快速点餐；浏览古着区，若线上有展示可提前锁定目标 | 高复购率，是品牌口碑传播的关键节点 |
| 本地顾客-小王（学生/自习者） | 15岁，价格敏感，需要安静、高效的体验，常消费午市套餐、咖喱饭 | 午休自习，快速下单用餐，不希望被打扰 | 稳定日常客流，提升非高峰时段利用率 |
| 境外顾客-Aki（日本复古爱好者） | 20岁，热衷80s美国复古风，通过TikTok/Ins发现潮物，信任商品细节与真实性 | 在TikTok看到商品视频后，跳转网站完成购买；关注品牌、年代、尺寸和瑕疵细节 | 开拓全新收入渠道，提升品牌国际影响力 |

---

## 核心业务流程图

是

否

是

否

顾客扫描桌码

进入点餐首页

是否新用户?

弹出优惠券/快速注册

直接浏览菜单

选择菜品/自定义规格

加入购物车

继续加菜?

提交订单

选择支付方式微信/支付宝/会员余额

完成支付

后厨/吧台打印订单大屏显示订单号

用户等待取餐/送达

---

## 系统功能结构图

此图展示了产品的完整功能模块，并明确了最小可行产品（MVP）的范围。

---

## 核心实体关系图

此图定义了系统数据库中最核心的实体及其关系，是后端开发的蓝图。

places

contains

included_in

USERS

string

user_id

PK

string

login_method

decimal

member_balance

int

points

PRODUCTS

string

product_id

PK

string

product_name

string

product_type

decimal

price

int

stock

string

status

json

details

array

image_urls

ORDERS

string

order_id

PK

string

user_id

FK

string

order_type

decimal

total_amount

string

order_status

string

pickup_number

datetime

created_at

ORDER_ITEMS

string

item_id

PK

string

order_id

FK

string

product_id

FK

int

quantity

decimal

unit_price

json

specifications

---

## 项目阶段总结与建议

根据以上分析，我们对 首期MVP版本 达成以下共识：

优先打磨店内体验，提升点餐效率与数据化管理能力，为后期电商扩展打下坚实基础。

基于 Vue的独立H5网站，适配手机端，并开发一个功能聚焦的后台管理系统。

电商全功能（购物、境外支付、物流）、预约订座、积分系统、在线客服、会员营销工具。

这套文档和图表已经构成了一个非常扎实的起点。接下来，您可以将其提供给开发团队进行工作量评估和技术方案设计。

- 前台：多方式注册登录、会员充值、动态菜单、自定义点餐、购物车、多方式支付、订单状态追踪。
- 后台：数据仪表盘、菜单与商品管理（含古着）、订单处理、轮播图管理。

---

