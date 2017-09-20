age<-c(1,3,5,2,11,9,3,9,12,3)
weight<-c(4.4,5.3,7.2,5.2,8.5,7.3,6.0,10.4,10.2,6.1)
plot(age,weight)
cor(age,weight)

#查阅手册、包相关
help.start()
install.packages("vcd")
help(package="vcd")
library(vcd)
help("Arthritis")
Arthritis
example("Arithmetic")
q()

#向量
a<-c(1,7,8,4)
a[2:4]

cells<-c(1,26,24,68)
rnames<-c("R1","R2")
cnames<-c("C1","C2")
mymatrix<-matrix(cells,nrow=2,ncol=2,byrow=TRUE,dimnames=list(rnames,cnames))
mymatrix

#矩阵
y<-matrix(1:20,nrow=5,ncol=4)
y

#数组
dim1<-c("A1","A2")
dim2<-c("B1","B2","B3")
dim3<-c("C1","C2","C3","C4")
z<-array(1:24,c(2,3,4),dimnames=list(dim1,dim2,dim3))
z     

#数据框
patientID<-c(1,2,3,4)
age<-c(25,34,28,52)
diabetes<-c("Type1","Type2","Type1","Type1")
status<-c("Poor","Improved","Excellent","Poor")
patientdata<-data.frame(patientID,age,diabetes,status)
patientdata

#列联表
table(patientdata$diabetes,patientdata$status)

#简化数据框中变量引入写法，同attach()搭配detach()
#with中括号内的变量赋值为局部变量，全局可使用<<-赋值
with(patientdata,{
  summary(age) 
  plot(age,patientID)
})

#因子（名义型/有序型）转整数向量（具体根据字母顺序而定）
diabetes<-c("Type1","Type2","Type1","Type1")
diabetes<-factor(diabetes)

#同上，视为有序变量，并自动选择合适的统计方法
status<-c("Poor","Improved","Excellent","Poor")
status<-factor(status,ordered = TRUE)

#同上，指定levels选项覆盖默认排序
status<-c("Poor","Improved","Excellent","Poor")
status<-factor(status,ordered = TRUE,
               levels=c("Poor","Improved","Excellent"))


#代码2.6 因子的使用
patientID<-c(1,2,3,4)
age<-c(25,34,28,52)
diabetes<-c("Type1","Type2","Type1","Type1")
status<-c("Poor","Improved","Excellent","Poor")
diabetes<-factor(diabetes)
status<-factor(status,ordered = TRUE)
patientdata<-data.frame(patientID,age,diabetes,status)

str(patientdata) #显示对象结构
summary(patientdata) #显示对象统计概要

#列表
#代码2.7 创建一个列表
g<-"My First List"
h<-c(25,26,18,39)
j<-matrix(1:10,nrow = 5)
k<-c("one","two","three")
mylist<-list(title=g,ages=h,j,k)
mylist

mylist[[2]]
mylist[["ages"]]

getwd()

#键盘输入数据
mydata<-data.frame(age=numeric(0),gender=character(0),weight==numeric(0))
mydata<-edit(mydata)

































