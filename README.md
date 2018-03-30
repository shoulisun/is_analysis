# 实验1 业务流程建模
|    学号    |       班级       |      姓名     |    照片    | 
|:-------:|:------------- | ----------:|----------:|
|   201510414314  |     2015级3班    |   孙守利   |  ![](./psb.jpg '描述') |


流程图1：考试及成绩管理流程
---------------
##### plantUML源码如下：
```
@startuml
|教务处|
start
 :安排考试;
 :考试安排表]
|教师|
 :出卷;
 split
  :A、B试卷]
 split again
  :打印审批表]
|系主任|
  :审批签字;
  :打印审批表]
 end split
|教务处|
 :打印试卷;
 :试卷]
|学生|
 :参加考试;
 :答卷]
|教师|
 :阅卷出成绩;
 fork
  :成绩单]
|教务处|
  if(有不及格？)then(有)
   :安排补考;
   :补考安排表]
  else(无)
  endif
 fork again
|教师|
  :答卷]
  :装订存档;
 endfork
 :期末流程结束;
stop
@enduml
```
##### 业务流程图如下：
![](./flow1.png '描述')
##### 流程说明：
`图6.1按不同的使用者（用户类别）分成了4行，图6.2按不同的用户类别分成了4列， 如何在建模中区分各功能的使用者？`
`答：使用”|用户类型|“区分各个功能的使用者`
`图6.1中有同步功能“A、B试卷”和“打印审批表”等，图6.2也有同步功能“安排工人”和“安排材料”，如何在建模中绘制？`
`答：使用“fork”“fork again”以及“endfork”来绘制同步功能`

流程图2：客户维修服务流程
---------------
##### palntUML源码如下：
```
@startuml
|客户|
start
 :申请服务;
|业务经理|
 if(是新客户吗？)then(是)
  :登记客户信息;
 else(不是)
 endif
 :上门勘察;
 :制定方案;
|客户|
 if(满意吗？)then(否)
  stop
 else(是)
  :签订服务合同;
|业务经理|
 fork
  :安排工人;
 fork again
  :安排材料;
 endfork
 :填写派工单;
|工人|
 :领取材料;
 :上门服务;
|客户|
 :验收并填写反馈意见;
|业务经理|
 :交回派工单;
|财务人员|
 :结算收款;
stop
@enduml
```
##### 业务流程图如下：
![](./flow2.png '描述')
##### 流程说明：
`说明如同考试及成绩管理业务流程，绘制方法大同小异`














