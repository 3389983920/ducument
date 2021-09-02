#相关函数指导

select * from pg_available_extensions where name = 'pgcrypto' or name = 'uuid-ossp';
-- uuid依赖
create extension "pgcrypto";
create extension "uuid-ossp"
-- 创建uuid 36位
select gen_random_uuid();
select uuid_generate_v4();

#递归查询语句


  >语句查询并替换
  ```代码语句块
  SELECT URL FROM "T_SYS_RESOURCE" WHERE URL like 'http://192.168.80.5:5000%';

  SELECT SUBSTR(URL, 0, 26) FROM "T_SYS_RESOURCE" WHERE URL like 'http://103.203.219.34:3003%';


  SELECT replace(URL,'http://103.203.219.34:3003','http://10.100.50.12') as a FROM "T_SYS_RESOURCE" WHERE URL like 'http://103.203.219.34:3003%';

  update T_SYS_RESOURCE set url = replace(URL,'http://192.168.80.5:5000','http://10.100.50.12') 
  WHERE URL like 'http://192.168.80.5:5000%';
  



