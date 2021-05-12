相关函数指导

select * from pg_available_extensions where name = 'pgcrypto' or name = 'uuid-ossp';
-- uuid依赖
create extension "pgcrypto";
create extension "uuid-ossp"
创建uuid 36位
select gen_random_uuid();
select uuid_generate_v4();

