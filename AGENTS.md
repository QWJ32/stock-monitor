# AGENTS.md

## 项目定位
本项目是 A 股策略模拟盘系统，只做模拟交易，不连接真实券商，不产生真实交易。

## 后端技术栈
Java Spring Boot 3
MySQL 8
Redis
MyBatis Plus
REST API

## 核心规则
策略不能写死在代码里，必须读取策略参数。
买入时必须保存 strategyParamsSnapshot。
已有持仓执行买入时的策略快照，不受后续策略修改影响。
行情第一阶段使用 Mock，后续预留第三方 HTTP 实时行情接口。
策略引擎每 3 秒扫描持仓。
T+1 第一阶段可先用 buyDate == currentDate 判断，但必须预留 TradingCalendarService。
不要实现登录注册。
不要实现真实券商交易。
不要修改前端代码。
每次修改后必须保证项目能编译通过。
