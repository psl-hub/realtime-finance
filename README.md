# -realtime-finance-warehouse
项目描述：基于金融信贷业务流程，搭建实时数据处理链路，实现从用户借款申请 → 三级风控审批 → 授信额度计算 → 合同生成与签约全流程实时化。保证审批低延迟、数据一致性、流程可追溯，支撑信贷业务高并发、稳定运行。 掌握实时大数据技术栈：Flink + Kafka 主流实时架构；理解金融风控业务逻辑；能支撑高并发申请场景，实现低延迟审批与授信，提升业务处理效率与用户体验。
项目内容：使用 Maxwell 解析 MySQL binlog，结合 Kafka 实现高并发实时数据接入；基于 FlinkCDC 完成 MySQL 变更数据的合并与过滤，实时写入 HBase 构建 DIM 层数据；通过 Flink 流计算将业务数据状态实时写入 Kafka 对应主题，构建事务实时表；在 DWS 层借助 Redis 缓存维度数据，使用 FlinkSQL 对 Kafka 流数据进行窗口聚合，实时计算用户近 30 天累计申请额等动态特征；将聚合结果写入 Doris，对外提供后端接口，并基于 Sugar 可视化工具搭建监控看板，支持业务指标实时查询与分析。
技术栈：Hadoop,zookeeper,MySQL,Maxwell,Kafka,Hbase,Flink,Maven,Redis,Doris,Sugar
金融审批业务数据源：<img width="2115" height="304" alt="屏幕截图 2026-04-02 115243" src="https://github.com/user-attachments/assets/a4413eab-9b53-44bd-a7c9-510e30848c28" />
实时金融审批大数据技术工具：<img width="1074" height="639" alt="屏幕截图 2026-04-02 120230" src="https://github.com/user-attachments/assets/8ce73539-f5c4-4e84-9ed7-0310d1fde949" />
flinkcdc实时流传输数据hbase，构建DIM数据层：<img width="1090" height="238" alt="屏幕截图 2026-04-02 124648" src="https://github.com/user-attachments/assets/28aeeafc-ab10-44e1-9cdc-5d81b9591d50" />
各审批业务流程传输对应kafka主题，构建DWD数据层：<img width="1054" height="360" alt="屏幕截图 2026-04-02 124948" src="https://github.com/user-attachments/assets/2f9c3228-0b48-4038-9b24-e45185c48e62" />
FlinkSQL 对 Kafka 流数据进行窗口聚合执行部分图：<img width="1365" height="400" alt="屏幕截图 2026-04-02 144059" src="https://github.com/user-attachments/assets/560d4beb-7730-460b-9f62-4e4d45a0b164" />
<img width="2256" height="1025" alt="屏幕截图 2026-04-02 143954" src="https://github.com/user-attachments/assets/50b297a3-18ad-486e-80a2-9046ffb57a65" />
通过Spring Boot 封装数据服务层进行内网穿透对外提供后端API接口给sugarBI进行数据分析：<img width="2286" height="1157" alt="屏幕截图 2026-04-02 201516" src="https://github.com/user-attachments/assets/e1ec4d14-2fb6-4707-aba9-1ed6de70bb93" />
<img width="2377" height="1139" alt="屏幕截图 2026-04-02 203322" src="https://github.com/user-attachments/assets/6f8afdf4-9c7f-400b-b657-a76fb2f34912" />
将各审批业务计算结果数据实时传入doris，构建DWS数据层：<img width="2370" height="1138" alt="屏幕截图 2026-04-02 181738" src="https://github.com/user-attachments/assets/98544952-04d9-4fc5-b162-5ba4bed84aec" />
<img width="2484" height="1054" alt="屏幕截图 2026-04-02 181818" src="https://github.com/user-attachments/assets/f4f0ab24-2718-4e40-a9db-c390b8e60b6a" />
<img width="2516" height="1158" alt="屏幕截图 2026-04-02 203730" src="https://github.com/user-attachments/assets/2fea0c58-513b-4790-b5e3-5ce1f7497321" />
配置sugar参数连接数据创建可视化报表：<img width="1668" height="621" alt="屏幕截图 2026-04-02 202505" src="https://github.com/user-attachments/assets/ee371f1c-7f27-408e-b9af-152d56d2d4ad" />
<img width="1369" height="624" alt="屏幕截图 2026-04-02 202916" src="https://github.com/user-attachments/assets/f4d712d0-76aa-4e68-be46-b17c5626d3bd" />
