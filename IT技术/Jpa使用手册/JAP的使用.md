### JPA

### 什么是JPA

[[JPA]] 的概念。


### 配置 

#### 配置数据源

在`application.properties`里配置数据源。


`spring.datasource.url=`
`spring.datasource.username=` 
`spring.datasource.password=` 



#### 建立Repository文件

```java
@Repository  
public interface EquipmentDetailRepository extends JpaRepository<CashierEquipmentDetail, Integer>,  
        JpaSpecificationExecutor<CashierEquipmentDetail> {

		/**  
 * 批量查询下的信息 * * @param storeId 店铺Id  
 * @param adminId 总部id  
 * @param type 类型  
 * @return  
 */  
int countByStoreIdAndAdminIdAndType(String storeId, String adminId, Integer type);
		
		}

```



#### 编写查询

一些我们可以利用JPA提供给我们的方式，实现简单查询
[[基础查询]]

在实际的开发中我们需要用到分页、删选、连表等查询的时候就需要特殊的方法或者自定义 SQL
[[复杂查询]]



### 多数据源支持

多数据源包含[[同源数据库的多源支持]] 和 [[异构数据库多源支持]]  
