# wordpress表 博客基础表

## 表的结构 wp_commentmeta
### 评论元数据表

| 字段 | 类型 | 空 | 默认 | 注释 |
| --- | --- | --- | --- | --- |
| meta_id | bigint(20) | 否 |   |   |
| comment_id | bigint(20) | 否 | 0 | 评论id |
| meta_key | varchar(255) | 是 | NULL | 键名 |
| meta_value | longtext | 是 | NULL | 键值 |

## 表的结构 wp_comments
### 评论表

| 字段 | 类型 | 空 | 默认 | 注释 |
| --- | --- | --- | --- | --- |
| comment_ID | bigint(20) | 否 |   | 评论id |
| comment_post_ID | bigint(20) | 否 | 0 | 评论文章id |
| comment_author | tinytext | 否 |   | 评论者 |
| comment_author_email | varchar(100) | 否 |   | 评论者email |
| comment_author_url | varchar(200) | 否 |   | 评论者url |
| comment_author_IP | varchar(100) | 否 |   | 评论者ip |
| comment_date | datetime | 否 | 0000-00-00 00:00:00 | 评论时间 |
| comment_date_gmt | datetime | 否 | 0000-00-00 00:00:00 | 评论时间（GMT+0时间）|
| comment_content | text | 否 |   | 评论内容 |
| comment_karma | int(11) | 否 | 0 | ？ |
| comment_approved | varchar(20) | 否 | 1 | 评论是否被批准 |
| comment_agent | varchar(255) | 否 |   | 评论者的USER AGENT |
| comment_type | varchar(20) | 否 |   | 评论类型 |
| comment_parent | bigint(20) | 否 | 0 | 父评论ID |
| user_id | bigint(20) | 否 | 0 | 评论者用户ID（不一定存在） |

## 表的结构 wp_links
### 友情链接表

| 字段 | 类型 | 空 | 默认 | 注释 |
| --- | --- | --- | --- | --- |
| link_id | bigint(20) | 否 |   |   |
| link_url | varchar(255) | 否 |   | 链接URL |
| link_name | varchar(255) | 否 |   | 链接标题 |
| link_image | varchar(255) | 否 |   | 链接图片 |
| link_target | varchar(25) | 否 |   | 链接打开方式 |
| link_description | varchar(255) | 否 |   | 链接描述 |
| link_visible | varchar(20) | 否 | Y | 是否可见（Y/N) |
| link_owner | bigint(20) | 否 | 1 | 添加者用户ID |
| link_rating | int(11) | 否 | 0 | 评分等级 |
| link_updated | datetime | 否 | 0000-00-00 00:00:00 | 创建时间 |
| link_rel | varchar(255) | 否 |   | XFN关系 |
| link_notes | mediumtext | 否 |   | XFN注释 |
| link_rss | varchar(255) | 否 |   | 链接RSS地址 |

## 表的结构 wp_options
### 存储WordPress系统选项和插件、主题配置
### 在多博客系统会多一个博客id

| 字段 | 类型 | 空 | 默认 | 注释 |
| --- | --- | --- | --- | --- |
| option_id | bigint(20) | 否 |   |   |
| option_name | varchar(191) | 否 |   | 键名 |
| option_value | longtext | 否 |   | 键值 |
| autoload | varchar(20) | 否 | yes | 在WordPress载入时自动载入（yes/no） |

## 表的结构 wp_postmeta
### 存储文章（包括页面、上传文件、修订）的元数据

| 字段 | 类型 | 空 | 默认 | 注释 |
| --- | --- | --- | --- | --- |
| meta_id | bigint(20) | 否 |   |   |
| post_id | bigint(20) | 否 | 0 | 对应文章ID |
| meta_key | varchar(255) | 是 | NULL | 键名 |
| meta_value | longtext | 是 | NULL | 键值 |

## 表的结构 wp_posts
### 存储文章（包括页面、上传文件、修订）

| 字段 | 类型 | 空 | 默认 | 注释 |
| --- | --- | --- | --- | --- |
| ID | bigint(20) | 否 |   |   |
| post_author | bigint(20) | 否 | 0 | 作者id |
| post_date | datetime | 否 | 0000-00-00 00:00:00 | 发布时间 |
| post_date_gmt | datetime | 否 | 0000-00-00 00:00:00 | 发布时间(GMT+0时间)|
| post_content | longtext | 否 |   | 内容 |
| post_title | text | 否 |   | 标题 |
| post_excerpt | text | 否 |   | 摘录 |
| post_status | varchar(20) | 否 | publish | 文章状态（publish/auto-draft/inherit等） |
| comment_status | varchar(20) | 否 | open | 评论状态(open/closed)|
| ping_status | varchar(20) | 否 | open | ping状态(open/closed) |
| post_password | varchar(20) | 否 |   | 文章密码 |
| post_name | varchar(200) | 否 |   | 文章缩略名 |
| to_ping | text | 否 |   | ？ 向什么地方ping |
| pinged | text | 否 |   | 已经PING过的链接 |
| post_modified | datetime | 否 | 0000-00-00 00:00:00 | 修改时间 |
| post_modified_gmt | datetime | 否 | 0000-00-00 00:00:00 | 修改时间(GMT+0时间) |
| post_content_filtered | longtext | 否 |   | ?内容过滤后的文本 |
| post_parent | bigint(20) | 否 | 0 | 父文章，主要用于page |
| guid | varchar(255) | 否 |   | ？组用户id |
| menu_order | int(11) | 否 | 0 | 排序ID |
| post_type | varchar(20) | 否 | post | 文章类型（post/page等）|
| post_mime_type | varchar(100) | 否 |   | MIME类型 |
| comment_count | bigint(20) | 否 | 0 | 评论总数 |

## 表的结构 wp_termmeta
### 存储每个目录、标签元数据
#### 这个表在旧版本是没有的

| 字段 | 类型 | 空 | 默认 | 注释 |
| --- | --- | --- | --- | --- |
| meta_id | bigint(20) | 否 |   |   |
| term_id | bigint(20) | 否 | 0 | 分类id |
| meta_key | varchar(255) | 是 | NULL | 键名 |
| meta_value | longtext | 是 | NULL | 键值 |

## 表的结构 wp_terms
### 存储每个目录、标签

| 字段 | 类型 | 空 | 默认 | 注释 |
| --- | --- | --- | --- | --- |
| term_id | bigint(20) | 否 |   | 分类id |
| name | varchar(200) | 否 |   | 分类名 |
| slug | varchar(200) | 否 |   | 别名 |
| term_group | bigint(10) | 否 | 0 | ？分类组 |

## 表的结构 wp_term_relationships
### 存储每个文章、链接和对应分类的关系

| 字段 | 类型 | 空 | 默认 | 注释 |
| --- | --- | --- | --- | --- |
| object_id | bigint(20) | 否 | 0 | 对应文章ID/链接ID |
| term_taxonomy_id | bigint(20) | 否 | 0 | 对应分类方法ID |
| term_order | int(11) | 否 | 0 | 排序 |

## 表的结构 wp_term_taxonomy
### 存储每个目录、标签所对应的分类

| 字段 | 类型 | 空 | 默认 | 注释 |
| --- | --- | --- | --- | --- |
| term_taxonomy_id | bigint(20) | 否 |   |   |
| term_id | bigint(20) | 否 | 0 | 分类id |
| taxonomy | varchar(32) | 否 |   | 分类方法(category/post_tag) |
| description | longtext | 否 |   | 介绍 |
| parent | bigint(20) | 否 | 0 | 所属父分类方法ID |
| count | bigint(20) | 否 | 0 | 文章数 |

## 表的结构 wp_usermeta
### 存储用户的元数据

| 字段 | 类型 | 空 | 默认 | 注释 |
| --- | --- | --- | --- | --- |
| umeta_id | bigint(20) | 否 |   |   |
| user_id | bigint(20) | 否 | 0 | 用户id |
| meta_key | varchar(255) | 是 | NULL | 键名 |  
| meta_value | longtext | 是 | NULL | 键值 |

## 表的结构 wp_users
### 用户

| 字段 | 类型 | 空 | 默认 | 注释 |
| --- | --- | --- | --- | --- |
| ID | bigint(20) | 否 |   |   |
| user_login | varchar(60) | 否 |   | 登录名 |
| user_pass | varchar(255) | 否 |   | 密码 |
| user_nicename | varchar(50) | 否 |   | 昵称 |
| user_email | varchar(100) | 否 |   | email |
| user_url | varchar(100) | 否 |   | 网址 |
| user_registered | datetime | 否 | 0000-00-00 00:00:00 | 注册时间 |
| user_activation_key | varchar(255) | 否 |   | 激活码 |
| user_status | int(11) | 否 | 0 | 状态 |
| display_name | varchar(250) | 否 |   | 显示名称 |
