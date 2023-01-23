cmake_minimum_required(VERSION 3.22)
cmake_policy(VERSION 3.22)

project("RenderingPlugin" CXX)

add_library(${PROJECT_NAME} MODULE)

target_compile_definitions(${PROJECT_NAME}
	PRIVATE
		-DSUPPORT_OPENGL_UNIFIED=1
		-DUNITY_LINUX=1
)
target_compile_options(${PROJECT_NAME} 
	PRIVATE
		-O2
		-fPIC
)

target_sources(${PROJECT_NAME} PRIVATE ../../source/RenderingPlugin.cpp ../../source/RenderAPI.cpp ../../source/RenderAPI_OpenGLCoreES.cpp)
