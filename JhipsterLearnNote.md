
## JDL使用方法
- Jhipster也支持redis缓存

- Jhipster手动删除实体类需要配合git删除才能删除干净

- Jhipster建实体类一般使用OneToOne、OneToMany、ManyToMany
 

- 利用jdl覆盖实体类时可能会出现bug，是日志文件出现问题，因此jhipster覆盖出错时，可以使用git回退，然后使用新生成的方式  
https://babuwant2do.wordpress.com/2017/09/06/jhipster-error-in-liquibase-changelog-generation/  

- OneToOne关系：  

```
X to Y
```

此时X是带有外键的表

- OneToMany关系

```
X to Y
```

此时Y是带有外键的表

- ManyToMany关系
```
X to Y
```
此时会自动新建一张中间表x_y存放两者外键

下面表示UserRole会使用RoleName的一个字段，此处是id即主键作为连接条件  
RoleName后面没有选项，因此会自动在UserRole表里生成一个新字段role_name_id作为连接条件

```
relationship OneToOne {
	UserRole{roleName(id)} to RoleName
}
```