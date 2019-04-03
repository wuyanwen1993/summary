# laravel 5.5 学习

## 开发环境配置

### vagrant 常用命令

| vagrant init      | 初始化 vagrant                              |
| ----------------- | ------------------------------------------- |
| vagrant up        | 启动 vagrant                                |
| vagrant halt      | 关闭 vagrant                                |
| vagrant ssh       | 通过 SSH 登录 vagrant（需要先启动 vagrant） |
| vagrant provision | 重新应用更改 vagrant 配置                   |
| vagrant destroy   | 删除 vagrant                                |


## Artisan 命令

是laravel 提供的CLI(命令行接口)

| php artisan key:generate     | 生成 App Key     |
| ---------------------------- | ---------------- |
| php artisan make:controller  | 生成控制器       |
| php artisan make:model       | 生成模型         |
| php artisan make:policy      | 生成授权策略     |
| php artisan make:seeder      | 生成 Seeder 文件 |
| php artisan migrate          | 执行迁移         |
| php artisan migrate:rollback | 回滚迁移         |
| php artisan migrate:refresh  | 重置数据库       |
| php artisan db:seed          | 填充数据库       |
| php artisan tinker           | 进入 tinker 环境 |
| php artisan route:list       | 查看路由列表     |

可以使用 `artisan lsit`  来查看所有可用的Artisan 命令

可以使用 `php artisan help migrate`来查看具体命令的帮助页面



生成控制器

php artisan make:controller StaticPagesController



Q&&A

npm run watch-poll 终端持续运行 监控resource 文件夹下的资源文件是否发生改变







