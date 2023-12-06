idf_build_get_property(target IDF_TARGET)

idf_component_register(
    SRCS "jsoncpp/src/lib_json/json_reader.cpp" "jsoncpp/src/lib_json/json_value.cpp" "jsoncpp/src/lib_json/json_writer.cpp"
    INCLUDE_DIRS "jsoncpp/include"
)

if(NOT CONFIG_COMPILER_CXX_EXCEPTIONS)
    target_compile_definitions(${COMPONENT_LIB} PUBLIC JSON_USE_EXCEPTION=0)
endif()
