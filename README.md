
### 说明

代码以阿里datax为基础，专注实现gis数据的读写，详情请参考datax[https://github.com/alibaba/DataX]

### 思路

读取：shape字段调用数据库函数转wkt字符串，例如：oracle数据库的sde.st_astext(shape)
写入：调用对应数据库的空间函数将wkt字符串转成图形存储到shape字段，例如：oracle数据库的sde.st_geomfromtext(wkt,wkid)或者sde.st_geometry(wkt,wkid)

### 修改
#### Writer
- 增加geometry相关配置，详情参见oracleWriter的plugin_job_template.json
- 修改shape读取到的原始类型信息，按照VARCHAR类型处理,相关文件：【com/alibaba/datax/plugin/rdbms/util/DBUtil.java  570行】
- 修改shape字段insert时占位符，默认为“?”,修改为“空间处理函数(?,wkid)”，相关文件：【com/alibaba/datax/plugin/rdbms/writer/util/OriginalConfPretreatmentUtil.java 165行】







