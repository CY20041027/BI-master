
## 项目介绍
BI （http://bi.hejiajun.icu）是一个在线数据分析和图表显示网站，用户只需上传原始数据集和输入分析目标即可调用 AI 生成与数据集相关的可视化图表。同时还支持用户创建和加入队伍，允许用户将已生成图表纳入队伍中，支持修改和重新生成队伍内其他图表。
### 项目效果图

![image-20250106123130915](https://hejiajun-img-bucket.oss-cn-wuhan-lr.aliyuncs.com/img/image-20250106123130915.png)

![image-20250106122249676](https://hejiajun-img-bucket.oss-cn-wuhan-lr.aliyuncs.com/img/image-20250106122249676.png)

![image-20250106124817118](https://hejiajun-img-bucket.oss-cn-wuhan-lr.aliyuncs.com/img/image-20250106124817118.png)

![image-20250106124615615](https://hejiajun-img-bucket.oss-cn-wuhan-lr.aliyuncs.com/img/image-20250106124615615.png)

![image-20250106123100878](https://hejiajun-img-bucket.oss-cn-wuhan-lr.aliyuncs.com/img/image-20250106123100878.png)

![image-20250106142404007](https://hejiajun-img-bucket.oss-cn-wuhan-lr.aliyuncs.com/img/image-20250106142404007.png)

### 项目架构图

![image-20250106121404827](https://hejiajun-img-bucket.oss-cn-wuhan-lr.aliyuncs.com/img/image-20250106121404827.png)



### MQ 架构图

![rabbitmq-structure](https://hejiajun-img-bucket.oss-cn-wuhan-lr.aliyuncs.com/img/rabbitmq-structure.jpg)



## 新增功能

1. MQ 消费者扩展至两个：分别是智谱 AI 与 ChatGPT-4o-mini，提供接口并发能力还加强了图表生成的准确性
2. 支持创建队伍和加入队伍：用户可以将已生成的图表纳入队伍中进行团队协作
3. 图表实时显示：引入 SSE 技术，当图表生成完毕会通过 SSE 流讲数据推送至前端，并完成实时渲染。（我的图表页面和队伍图表页面都支持）
4. 后台管理：新增用户管理、图表管理和队伍管理页面。当图表生成错误时，管理员可以查看图表生成状态，既可以在线修改 Echarts 代码，也能重新生成图表，但走的时管理员专属队列，不会扣除用户积分。
5. 限制用户同时生成的数量，保证系统可用性。
6. 优化 AI prompt：规范 AI 输出格式，提升 AI 生成代码的合法性和正确性。
