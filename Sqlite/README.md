��ӣ�
	insert into person (name, number) values ('zhangsan', '110')

��ѯ��
	ȫ�� select * from person
	���� select * from person where name = 'zhangsan'

�޸ģ�
	update person set number = '119'  where name = 'zhangsan'
	alter table person add account varchar(20)	Ϊ��������һ��account
ɾ����
	delete from person where name = 'zhangsan'