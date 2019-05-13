# mtm项目简介
MySql数据库表装换Go Struct(mysql to model)简称(mtm)
大型项目，一般采用数据库先行的设计方式，该工具很好的实现了从数据库到Go Struct代码的转换，减少了手动写Struct的时间。
# 使用方法
#### 获取
go get github.com/xianghu1314/mtm
#### 调用
```$xslt
	//模型转换
	t2s := mtm.CreateTableToStruct(&mtm.Options{
		MySqlUrl:                "XXX",
		FileName:                "Models.go",
		IfOneFile:               true,
		PackageName:             "Models",
		SavePath:                "./Models",
		IfToHump:                true,
		IfJsonTag:               true,
		IfPluralToSingular:      true,
		IfCapitalizeFirstLetter: true,
	})
	err := t2s.Run()
	if err != nil {
		log.Fatal("模型转换：" + err.Error())
	}
```
