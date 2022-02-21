<table>
<thead>
<tr>
<th>Keyword</th>
<th>Sample</th>
<th>JPQL snippet</th>
</tr>
</thead>
<tbody>
<tr>
<td>And</td>
<td>findByLastnameAndFirstname</td>
<td>… where x.lastname = ?1 and x.firstname = ?2</td>
</tr>
<tr>
<td>Or</td>
<td>findByLastnameOrFirstname</td>
<td>… where x.lastname = ?1 or x.firstname = ?2</td>
</tr>
<tr>
<td>Is,Equals</td>
<td>findByFirstnameIs,findByFirstnameEquals</td>
<td>… where x.firstname = ?1</td>
</tr>
<tr>
<td>Between</td>
<td>findByStartDateBetween</td>
<td>… where x.startDate between ?1 and ?2</td>
</tr>
<tr>
<td>LessThan</td>
<td>findByAgeLessThan</td>
<td>… where x.age &lt; ?1</td>
</tr>
<tr>
<td>LessThanEqual</td>
<td>findByAgeLessThanEqual</td>
<td>… where x.age ⇐ ?1</td>
</tr>
<tr>
<td>GreaterThan</td>
<td>findByAgeGreaterThan</td>
<td>… where x.age &gt; ?1</td>
</tr>
<tr>
<td>GreaterThanEqual</td>
<td>findByAgeGreaterThanEqual</td>
<td>… where x.age &gt;= ?1</td>
</tr>
<tr>
<td>After</td>
<td>findByStartDateAfter</td>
<td>… where x.startDate &gt; ?1</td>
</tr>
<tr>
<td>Before</td>
<td>findByStartDateBefore</td>
<td>… where x.startDate &lt; ?1</td>
</tr>
<tr>
<td>IsNull</td>
<td>findByAgeIsNull</td>
<td>… where x.age is null</td>
</tr>
<tr>
<td>IsNotNull,NotNull</td>
<td>findByAge(Is)NotNull</td>
<td>… where x.age not null</td>
</tr>
<tr>
<td>Like</td>
<td>findByFirstnameLike</td>
<td>… where x.firstname like ?1</td>
</tr>
<tr>
<td>NotLike</td>
<td>findByFirstnameNotLike</td>
<td>… where x.firstname not like ?1</td>
</tr>
<tr>
<td>StartingWith</td>
<td>findByFirstnameStartingWith</td>
<td>… where x.firstname like ?1&nbsp;(parameter bound with appended&nbsp;%)</td>
</tr>
<tr>
<td>EndingWith</td>
<td>findByFirstnameEndingWith</td>
<td>… where x.firstname like ?1&nbsp;(parameter bound with prepended&nbsp;%)</td>
</tr>
<tr>
<td>Containing</td>
<td>findByFirstnameContaining</td>
<td>… where x.firstname like ?1&nbsp;(parameter bound wrapped in&nbsp;%)</td>
</tr>
<tr>
<td>OrderBy</td>
<td>findByAgeOrderByLastnameDesc</td>
<td>… where x.age = ?1 order by x.lastname desc</td>
</tr>
<tr>
<td>Not</td>
<td>findByLastnameNot</td>
<td>… where x.lastname &lt;&gt; ?1</td>
</tr>
<tr>
<td>In</td>
<td>findByAgeIn(Collection<age> ages)</age></td>
<td>… where x.age in ?1</td>
</tr>
<tr>
<td>NotIn</td>
<td>findByAgeNotIn(Collection<age> age)</age></td>
<td>… where x.age not in ?1</td>
</tr>
<tr>
<td>TRUE</td>
<td>findByActiveTrue()</td>
<td>… where x.active = true</td>
</tr>
<tr>
<td>FALSE</td>
<td>findByActiveFalse()</td>
<td>… where x.active = false</td>
</tr>
<tr>
<td>IgnoreCase</td>
<td>findByFirstnameIgnoreCase</td>
<td>… where UPPER(x.firstame) = UPPER(?1)</td>
</tr>
</tbody>
</table>