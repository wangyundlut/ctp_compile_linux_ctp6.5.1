cmake_minimum_required(VERSION 3.5)

project(_thostmduserapi)
# 用于生成位置无关代码，代码无绝对跳转，跳转都为相对跳转
# add_compile_options(-fPIC)
# generate shared library
add_library(_thostmduserapi 
    SHARED 
    ThostFtdcMdApi.h
    ThostFtdcUserApiDataType.h
    ThostFtdcUserApiStruct.h
    thostmduserapi_wrap.cxx
    thostmduserapi_wrap.h
)

# header file
target_include_directories(_thostmduserapi
    PUBLIC 
        # /root/anaconda3/envs/python38/include/
        /root/anaconda3/envs/python38/include/python3.8/
        # ${PROJECT_SOURCE_DIR}/include
)
# lib 
target_link_libraries( _thostmduserapi
    PUBLIC 
        python3.8
        thostmduserapi_se
)


