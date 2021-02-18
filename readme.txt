# TradeAPi Linux Cmake + ctp6.5.1 #
# 1 下载交易所api 6.5.1 #
# 2 swig 编译 内容在.i 里面 #
其中包括字符转换
当前目录下运行cmd:

    swig -threads -py3 -c++ -python thosttraderapi.i
生成_wrap.h  
*_wrap.cxx  
thosttradeapi.py
# 3 CMake建立工程 #
	具体内容见CMake  
	工程名_thosttraderapi
	包含文件
	ThostFtdcTraderApi.h
	ThostFtdcUserApiDataType.h
	ThostFtdcUserApiStruct.h
	thosttraderapi.lib
	thosttraderapi_wrap.cxx
	thosttraderapi_wrap.h
	链接python静态库 和trader动态库
	
添加现有项 6个文件
然后 
	1 将python  头文件 在 include里 包含进来（可以创建虚拟环境包含进来） 
    2 将python.libs静态库文件夹包含进来
    3 添加静态库

编译 64位 release版本
# 4 测试 #

	

# MDAPI #
	mdapi中需要修改二级指针的转换
    2类似 第二步开始把所有的tradeapi改成mdapi
	swig -threads -c++ -python thostmduserapi.i
	
	

