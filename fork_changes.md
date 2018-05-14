- add by zyc
  + 分页信息增加pageSize选项
  + 修改为bootstrap风格，直接修改源码，不是按插件方方式
  + apendParams 去除key：params ,将appendParams直接放到根下
  + 回调函数原来只掉用到vuetable级别函数，这里增加$root函数，同时增加参数item；Vuetable.vue 1010行
