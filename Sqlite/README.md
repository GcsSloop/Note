添加：
	insert into person (name, number) values ('zhangsan', '110')

查询：
	全部 select * from person
	具体 select * from person where name = 'zhangsan'

修改：
	update person set number = '119'  where name = 'zhangsan'
	alter table person add account varchar(20)	为表中增加一列account
删除：
	delete from person where name = 'zhangsan'