# Jenkins_CI_Test
用于测试jenkins持续构建服务
目前想法：
第一步：自动获取gitlab或者github上某个项目push的内容
第二步：将第一步获取的内容打包成对应的版本（看看该版本是否能从push中获取到对应的时间以及push人员的信息打一个tage到对应的版本是上存储到服务器的某个文件中或者是oss服务器上）
第三步：如果测试哪一个版本到时候从版本库（对应存储的地方检索出来）直接部署到服务器中
第四步：部署过程完成之后触发接口自动化测试脚本或者是UI自动化脚本，这样对每个版本都会得到更好的测试

目前做到：
第一步：完成自动获取github某个项目push的内容
后续补充：操作文档
