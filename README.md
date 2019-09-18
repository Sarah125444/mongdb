# mongdb
## MongoDB
  + 关系型数据库和非关系型数据库
    + 表就是关系
    + 或者说表与表之间存在关系
      - 所有的关系型数据库都需要通过sql语言来操作
      - 所有的关系型数据库在操作之前都需要设计表结构
      - 而且数据表还支持约束
        + 唯一的
        + 主键
        + 默认值
        + 非空
    + 非关系型数据库非常的灵活
    + 有的非关系型数据库就是key-value对儿
    + 但是MongoDB是长得最像关系型数据库的非关系型数据库
      - 数据库 ==> 数据库
      - 数据表 ==> 集合（数据）
      - 表记录 ==> 文档对象
    + MongoDB不需要设计表结构
    + 也就是说你可以任意往里面存数据，没有结构性这么一说

### MongoDB安装与配置
  + 使用homebrew来安装
     + 查询下是否已经安装了brew
     ```
     brew --version
     ```
     + 更新brew
     ```
     brew updata
     ```
     + 安装
     ```
     brew install mongodb
     ```

  + 配置数据库
    + 首先创建保存数据的文件夹
    ```
    # mongdb默认使用执行mongdb命令所处盘符根目录下的/data/db作为自己的数据存储目录
    # 所以在第一次执行该命令之前先自己手动创建一个/data/db
    sudo mkdir -p /data/db
    ```
    如果想要修改默认的数据存储目录，可以使用下面的目录
    ```
    mongod --dbpath=数据存储目录
    ```

    + 然后给刚刚创建的文件夹写入数据权限
    ```
    sudo chown -R $USER /data/db
    ```

### 操作mongdb
    + 启动mongdb服务
      ```
      mongod
      ```
    + 停止
      在开启服务的控制台，直接ctrl+c即可停止
      或者直接关闭开启服务的控制台也可以

    + 连接和退出数据库
      + 连接
      ```
      # 该命令默认连接到本机的MongoDB服务
      mongo
      ```
      + 退出
      ```
      # 在连接状态输入exit退出连接
      exit
      ```
### MongoDB基本命令
    - 先使用命令mongo开启数据库服务，然后再这基础上再新开一个窗口，然后再mango开启服务，输入一下命令进行测试！
    - show dbs
      + 显示查看所有数据库
    - db
      + 查看当前操作的数据库
    - use 数据库
      + 切换到当前数据库（如果没有会新建）
      ```
      use itcast
      ```
    - 插入一条数据
      ```
      db.students.insertOne({"name": "Jack"})
      ```
    - 查看集合
      ```
      show collections
      ```
    - 查看插入的数据
      ```
       db.students.find()
      ```
### 在Node中如何操作MongoDB数据
    - 使用官方mongdb包来操作
      + github上可以搜索到
    - 使用第三方mongoose来操作MongDB数据库
      + 第三方包基于MongoDB官方的mongodb再一次做了封装
