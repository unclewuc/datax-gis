
# 说明

代码以阿里datax为基础，专注实现gis数据的读写，详情请参考datax[https://github.com/alibaba/DataX]


# 修改

    序号  |   文件位置    |   方法函数        |   行号  |   修改原因
    ----    |   ----    |   ----    |   ----    |   ----
    1   |  com/alibaba/datax/plugin/rdbms/util/DBUtil.java |   getColumnMetaData    |   570行    |   修改无法识别的列数据类型SDE.ST_GEOMETRY，按照VARCHAR处理





