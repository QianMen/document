首先创建一张表,用于存储用户的登陆信息,并向里面插入两条数据.
```
CREATE TABLE `users` (
`id` int(11) NOT NULL AUTO_INCREMENT,
`username` varchar(64) NOT NULL,
`password` varchar(64) NOT NULL,
`email`    varchar(64) NOT NULL,
PRIMARY KEY(`id`),
UNIQUE KEY `username` (`username`)
)ENGINE=MyISAM AUTO_INCREMENT=10000 DEFAULT CHARSET=latin1;

INSERT INTO users (username,password,email) VALUES ('GeekZhou',md5('testtest'),'15210001000@163.com');
INSERT INTO users (username,password,email) VALUES ('MarcoFly',md5('test'),'marcofly@test.com');
```
