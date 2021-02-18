cmake_minimum_required(VERSION 3.5)

project(_thosttraderapi)

# generate shared library
add_library(_thosttraderapi 
    SHARED 
    ThostFtdcTraderApi.h
    ThostFtdcUserApiDataType.h
    ThostFtdcUserApiStruct.h
    thosttraderapi_wrap.cxx
    thosttraderapi_wrap.h
)

# header file
target_include_directories(_thosttraderapi
    PUBLIC 
        # /root/anaconda3/envs/python38/include/
        /root/anaconda3/envs/python38/include/python3.8/
        # ${PROJECT_SOURCE_DIR}/include
)
# lib 
target_link_libraries( _thosttraderapi
    PUBLIC 
        python3.8
        thosttraderapi_se
)


