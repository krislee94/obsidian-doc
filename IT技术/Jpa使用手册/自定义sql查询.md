实 Spring Data 觉大部分的 SQL 都可以根据方法名定义的方式来实现，但是由于某些原因我们想使用自定义的 SQL 来查询，Spring Data 也是完美支持的；在 SQL 的查询方法上面使用`@Query`注解，如涉及到删除和修改在需要加上`@Modifying`.也可以根据需要添加 `@Transactional`对事务的支持，查询超时的设置等。

```java

@Modifying @Query("update User u set u.userName = ?1 where u.id = ?2")
int modifyByIdAndUserId(String userName, Long id);


```



```java
@Transactional @Modifying @Query("delete from User where id = ?1")
void deleteByUserId(Long id);

```



```java


@Transactional(timeout = 10) @Query("select u from User u where u.emailAddress = ?1") 

User findByEmailAddress(String emailAddress);

```