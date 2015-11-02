# Answer #

## todo-list ##
- 章节练习UI
- 收藏资料
- 上传资料
- 最新上传
- 资料库分类下属页面美化
- 积分管理
- 最热类型
- 个人头像
- 错题集
- 数据库控制首页banner

## 个人 ##
- 个人标题+二维码
- 我的红包
- 我的好友
- 我的收藏
- 我的下载
- 资料库
- 学习圈
- 错题集
- 计划

## 答题 ##
### 答题类型 ###
- 章节练习
- 考前模拟
- 真题检测

### 题目 ###
- 评分
- 分享
- 收藏
- 错题记录

## 资料 ##
- 找资料
- 资料库
	- 分类
- 上传资料
- 下载资料
- 热门类型
- 我的资料
- 最新上传

# 模块 #
## 所用APICloud模块列表 ##
- mcm
- UIScrollPicture
- UISearchBar
- FNScanner
- fs
- fileBrower
- downloadManager

# 数据库架构 #
## 数据库 ##
- QuestionBank 题库
	- title 题目标题
	- pic 题目图片
	- questionContent 题目内容*
	- answer1.2.3.4 回答选项*
	- trueanswer 正确答案*
- QuestionType 题目学科分类
	- name 学科名*
	- examination (关联Examination) 所有该学科下的试卷
	- chapter (关联Chapter) 所有该学科下的章节
	- unclassifiedQuestions (关联QuestionBank) 所有该学科下所有无类别的问题
- Score 得分
	- classifyScore 该分类的得分*
	- type (QuestionType) 该分类的索引*
- Chapter 学科章节
	- questions (关联QuestionBank) 该学科下所有题目
- Examination 测试题
	- questions (关联QuestionBank) 该试卷所有题目
- MessageBoard 留言板
	- content 留言内容*
	- userId (关联_user) 留言ID*
	- comment (关联MessageComment) 该留言评论集合
- MessageComment 留言板评论
	- content 留言内容*
	- userId (关联_user) 留言ID*
- Favorite 题目收藏
	- questionId (关联QuestionBank) 收藏的题目ID*
	- userId (关联_user) 该用户ID*
- Document 资料类
	- file 上传的文件*
	- uploadId 上传人ID
- DocumenType 资料分类
	- typeName 资料类型名*
	- document (关联Document) 资料
- Rank 排行榜
	- userId (关联_user) 该用户ID*
	- score 该用户积分