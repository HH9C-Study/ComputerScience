## ๐ฉ SQL(Structured Query Language)
DataBase๋ฅผ ๊ตฌ์ถํ๊ณ  ์ ๊ทผํ  ์ ์๊ฒ ์ฌ์ฉ๋๋ ์ธ์ด์ด๋ค. ๋ฏธ๊ตญ ๊ตญ๋ฆฝ ํ์ค ํํ๊ฐ SQL์ ํ์ค์ผ๋ก ์ฌ์ ํ์ฌ SQL์ด ๊ฐ์ฅ ๋ง์ด ์ฌ์ฉ๋๋ค.

#### SQL์ ์ข๋ฅ
SQL์ ์์ด ๋ฌธ์ฅ๊ณผ ์ ์ฌํด์ ์ด๋ณด์๋ค๋ ๋น๊ต์  ์ฝ๊ฒ ์ฌ์ฉ๊ฐ๋ฅํ๋ค.
ํฌ๊ฒ ์ ์์ธ์ด `DDL`, ๋ฐ์ดํฐ ์กฐ์์ธ์ด `DML`๋ก ๋๋๋ค.

| ๋ถ๋ฅ | ๋ด์ฉ |
|:----------:|:----------|
| ๋ฐ์ดํฐ ์ ์ ์ธ์ด (DDL, Data Definition Language) | ๋ฆด๋ ์ด์ ์์ฑ, ์ญ์ , ๋ณ๊ฒฝ |
| ๋ฐ์ดํฐ ์กฐ์ ์ธ์ด (DML, Data Manipulation Language) | ๊ฒ์, ์ฝ์, ์ญ์ , ๊ฐฑ์  |

#### โ Query
Query๋ ์ง๋ฌธ์ด๋ผ๋ ๋ป์ผ๋ก, ์ง์(inquiry)์ ๊ฐ์ ๋ป์ผ๋ก ์ฌ์ฉ๋๋ค.
ํ์ผ์ ๋ด์ฉ์ ์๊ธฐ ์ํด code๋ key๋ฅผ ๊ธฐ์ด๋ก ์ง์ํ๋ ๊ฒ์ ๊ฐ๋ฆฌํจ๋ค. DB์ ์กด์ฌํ๋ ์๋ฃ๋ฅผ ์ฌ์ฉ์๊ฐ ์ํ๋ ์กฐ๊ฑด์ ํตํด ๊ฒ์ํ๊ณ , ๊ฒ์๋ ๊ฒฐ๊ณผ๋ฅผ ์์ ๋ก์ด ์กฐํํ  ์ ์๋ ๊ธฐ๋ฅ๋ค์ ์ง์ํ๋ค. ์ด๋ฌํ ์ง์์ด๋ค์ด ๊ตฌ์กฐ์ ์ผ๋ก ์ฒด๊ณํ๋ ๊ฒ์ SQL์ด๋ผ๊ณ  ํ๋ค!

---

## ๐ช SQL Query๋ฌธ (Select & Where)
### 1. SELECT QUERY
Select ์ฟผ๋ฆฌ๋ฌธ์ `์ด๋ค ํ์ด๋ธ`์์ `์ด๋ค ํ๋์ ๋ฐ์ดํฐ`๋ฅผ ๊ฐ์ ธ์ฌ์ง๋ก ๊ตฌ์ฑ๋๋ค.
> Select ์ฟผ๋ฆฌ๋ฌธ์ ํตํด 'orders ํ์ด๋ธ์ created_at, course_title, payment_method, email ํ๋๋ฅผ ๊ฐ์ ธ์์ค!'๋ผ๊ณ  ๋ช๋ น์ ๋ด๋ฆด ์ ์๋ค.

```java
select * from orders;
select created_at, course_title, payment_method, email from orders;
```

### 2. Where ์ 
Where ์ ์ Select ์ฟผ๋ฆฌ๋ฌธ์ผ๋ก ๊ฐ์ ธ์ฌ ๋ฐ์ดํฐ์ ์กฐ๊ฑด์ ๊ฑธ์ด์ฃผ๋ ๊ฒ์ ์๋ฏธํ๋ค.

```java
select * from Orders
where payment method = 'kakaopay';
```

SQL๋ฌธ์ ์ค์ ์ ๋ง์ถฐ์ฃผ๋ ๊ฒ์ด ์ค์ํ๋ค. ๋์ค์ ์์ด ๋ฐฉ๋ํด์ง๋ฉด ๊ธธ์ด์ง๊ณ  ํท๊ฐ๋ฆฌ๊ธฐ ๋๋ฌธ์ด๋ค.

```java
select * from point_users
where point >= 5000
```

```java
select * from Orders
where course_title = '์ฑ๊ฐ๋ฐ ์ขํฉ๋ฐ' and payment_method = 'card'
where course_title = '์ฑ๊ฐ๋ฐ ์ขํฉ๋ฐ' or payment_method = 'card'
```

์ด์์ผ ๋ `>=`, ์ด๊ณผ์ผ ๋ `>` ์ด๋ ๊ฒ ํํํ๊ณ , `and`๋ `or`์ ์ฌ์ฉํ์ฌ ์กฐ๊ฑด์ ์ถ๊ฐํ  ์ ์๋ค.

### 3. Where ์ ๊ณผ ๊ฐ์ด ์ฐ์ด๋ ๋ฌธ๋ฒ
1) `!=` : ๊ฐ์ง ์์
2) `=` : ๊ฐ์
3) `between` `and` :  ~์ฌ์ด์ ์๋ ์ ๋ณด๋ฅผ ๋ณด๊ณ  ์ถ์ ๋ (๋ฒ์์กฐ๊ฑด)
4) `in(a,b,c,โขโขโข)` : a๋๋ b๋๋ C โขโขโข์ธ ๋ฐ์ดํฐ๋ฅผ ๋ณด๊ณ  ์ถ์ ๋ (ํฌํจ์กฐ๊ฑด)
5) `like` + `%` : ํจํด ๊ท์น (๋ฌธ์์ด ๊ท์น) 'how to use like in sql' ๊ตฌ๊ธ๋ง

```java
select * from users 
where email like '%daum.net';
```

### 4. ์ด์ธ ์ ์ฉํ ๋ฌธ๋ฒ
1) `Limit` : ์ผ๋ถ ๋ฐ์ดํฐ๋ง ๊ฐ์ ธ์ฌ ๋ 
```java
select * from orders 
where payment_method = "kakaopay"
limit 5;
```

2) `Distinct` : ์ค๋ณต๋ฐ์ดํฐ ์ ๊ฑฐ 
```java
select distinct(payment_method) from orders;
```

3) `Count` : ๋ช ๊ฐ์ธ์ง ์ซ์๋ฅผ ์ธ์ด๋ณผ ๋
```java
select count(*) from orders
```

4) `Distinct`์ `Count` ํ๋ฒ์ ์์ฑํด ๋ณด๊ธฐ
```java
select distinct(name) from users;
```

---

## ๐ SQL Query๋ฌธ (Group by & Order by)
### 1. Group by
```java
select name, count(*) from users
group by name;
```

1) from users: users ํ์ด๋ธ์์ ๋ฐ์ดํฐ๋ฅผ ๋ถ๋ฌ์จ๋ค
2) group by name: name์ด๋ผ๋ ํ๋์์ ๋์ผํ ๊ฐ์ ๊ฐ๋ ๋ฐ์ดํฐ๋ฅผ ํ๋๋ก ํฉ์ณ์ค๋ค
3) select `name`, `count(*)` : `์ด๋ฆ`๊ณผ `count(*)`๋ฅผ ์ถ๋ ฅํด ์ฃผ๋๋ฐ, ์ฌ๊ธฐ์ `count(*)`๋ `group by`๋ก ํฉ์ณ์ง ๋ฐ์ดํฐ์ ๊ฐ์๋ฅผ ์ธ์ด์ฃผ๋ ๊ฒ์ด๋ค.

### 2. Group by ๊ธฐ๋ฅ
1) `count`
```java
select ๋ฒ์ฃผ๋ณ๋ก ์ธ์ด์ฃผ๊ณ  ์ถ์ ํ๋๋ช, count(*) from ํ์ด๋ธ๋ช
group by ๋ฒ์ฃผ๋ณ๋ก ์ธ์ด์ฃผ๊ณ  ์ถ์ ํ๋๋ช;
```

2) `min`
```java
select ๋ฒ์ฃผ๊ฐ ๋ด๊ธด ํ๋๋ช, min(์ต์๊ฐ์ ์๊ณ  ์ถ์ ํ๋๋ช) from ํ์ด๋ธ๋ช
group by ๋ฒ์ฃผ๊ฐ ๋ด๊ธด ํ๋๋ช;
```

3) `max`
```java
select ๋ฒ์ฃผ๊ฐ ๋ด๊ธด ํ๋๋ช, max(์ต๋๊ฐ์ ์๊ณ  ์ถ์ ํ๋๋ช) from ํ์ด๋ธ๋ช
group by ๋ฒ์ฃผ๊ฐ ๋ด๊ธด ํ๋๋ช;
```

4) `avg`
```java
select ๋ฒ์ฃผ๊ฐ ๋ด๊ธด ํ๋๋ช, avg(ํ๊ท ๊ฐ์ ์๊ณ  ์ถ์ ํ๋๋ช) from ํ์ด๋ธ๋ช
group by ๋ฒ์ฃผ๊ฐ ๋ด๊ธด ํ๋๋ช;
```
avg์ ๊ฒฝ์ฐ ์์์ ์ด ๊ธธ๊ฒ ๋์ค๋ ๊ฒ์ ํด๊ฒฐํ๊ธฐ ์ํ์ฌ `round(avg(ํ๋๋ช),n))` ์ด๋ฐ ์์ผ๋ก avg๋ฅผ ๊ฐ์ธ๊ณ  n๊ฐ๊น์ง์ ์์์  ์๋ฆฌ๊ฐ ๋์ค๊ฒ ํ๋ค.

5) `sum`
```java
select ๋ฒ์ฃผ๊ฐ ๋ด๊ธด ํ๋๋ช, sum(ํฉ๊ณ๋ฅผ ์๊ณ  ์ถ์ ํ๋๋ช) from ํ์ด๋ธ๋ช
group by ๋ฒ์ฃผ๊ฐ ๋ด๊ธด ํ๋๋ช;
```

### 3. Order by
๋ฌธ์์ด ๊ธฐ์ค์ผ๋ก ์ ๋ ฌ, ์๊ฐ์ ๊ธฐ์ค์ผ๋ก ์ ๋ ฌ, ๊ฐ์ ํฌ๊ธฐ ๊ธฐ์ค์ผ๋ก ์ ๋ ฌ, ํ๊ธ๋ก ์ ๋ ฌ โขโขโข
๋ค ๊ฐ๋ฅํ๋ค!
```java
select * from ํ์ด๋ธ๋ช
order by ์ ๋ ฌ์ ๊ธฐ์ค์ด ๋  ํ๋๋ช;
```
`desc` : descending (๋ด๋ฆผ์ฐจ์)
`asc` : ascending (์ค๋ฆ์ฐจ์)	

SQL ์ฟผ๋ฆฌ๊ฐ ์คํ๋๋ ์์๋ฅผ ์์์ผ ์๋ฌ ์์ด ์ฟผ๋ฆฌ๋ฅผ ์์ฑํ  ์ ์๋ค.
select name, count(*) from users
group by name
order by count(*);
์ ์ฟผ๋ฆฌ๊ฐ ์คํ๋๋ ์์: from โ group by โ select โ order by


### 4. Alias
ํ์ด๋ธ์ ์๋ ๋ง์์ง๊ณ , ๋ฐ์ดํฐ์ ์๋ ๋ง์์ ธ์ ์ฟผ๋ฆฌ๊ฐ ์ ์  ๊ธธ์ด์ง๊ฒ ๋๋ฉด ํท๊ฐ๋ฆฌ๋ ์ผ์ด ๋ฐ์ํ๋ ๋๊ฐ ์๊ธด๋ค. ๊ทธ๋์ SQL์ Alias(์๋ฆฌ์์ค)๋ผ๋ ๋ณ์นญ ๊ธฐ๋ฅ์ ์ง์ํ๋ค.
```java
select * from orders o
where o.course_title = '์งฑ์ค์'
```

```java
select payment_method, count(*) as cnt from orders o
where o.course_title = '์งฑ์ค์'
group by payment_method
```

---

## ๐ฏ Table Join
์๋์ ์ฌ์ง๋ค ์ถ์ฒ : [cloudstudying.kr](https://cloudstudying.kr/lectures/502)

![](https://velog.velcdn.com/images/younseo1016/post/1acd01f1-dca6-4bfa-8356-d2b8f4ebfe49/image.png)

![](https://velog.velcdn.com/images/younseo1016/post/3579abae-278c-4ffc-8828-e8446e1372b1/image.png)

SQL์์์ Join์ ๋ ์งํฉ ์ฌ์ด์ ๊ด๊ณ์ ๊ฐ๋ค.

### 1. Left Join
![](https://velog.velcdn.com/images/younseo1016/post/441dbc29-e799-4d58-912e-7a7ef8dbe974/image.png)

์ ๊ทธ๋ฆผ์์ A์ B๋ ๊ฐ๊ฐ์ ํ์ด๋ธ์ ์๋ฏธํ๋ค. Left Join์ ๋ ํ์ด๋ธ์ ๊ณตํต๊ฒฐ๊ณผ ๋ฟ๋ง ์๋๋ผ, ์ข์ธก ํ์ด๋ธ์ ๋ชจ๋  ๊ฒฐ๊ณผ๋ ๊ฐ์ ธ์ค๋ ๊ฒ์ด๋ค. 
โ๋ชจ๋  ์ข์ธก ํ์ด๋ธ์ ๊ฐ์ ธ์ค๋๋ฐ, ์กฐ์ธ ๊ฐ๋ฅํ ๊ฒ์ ๋ถ์ด๊ณ , ์กฐ์ธ ๋ถ๊ฐ๋ฅํ ๊ฒ์ NULL๋ก ์ฑ์ด๋ค!โ
left join์ `์ด๋์ โ ๋ญ๋ฅผ ๋ถ์ผ ๊ฑด์ง` ์์๊ฐ ์ค์ํ๋ค.

### 2. Right Join
![](https://velog.velcdn.com/images/younseo1016/post/5bc86a70-9c31-4c3d-babd-4699eea11a87/image.png)

์ฐ์ธก ํ์ด๋ธ์ ๋ชจ๋  ๊ฒฐ๊ณผ๋ ๊ฐ์ ธ์ค๋ ๊ฒ์ด๋ค.

### 3. Full Join 
![](https://velog.velcdn.com/images/younseo1016/post/cac8776f-b1c2-4b89-ad10-70b036f0eb5e/image.png)

์กฐ์ธ ๊ฐ๋ฅํ ๋ฐ์ดํฐ ๋ฟ๋ง ์๋ ์กฐ์ธ ๋ถ๊ฐ๋ฅํ ๋ฐ์ดํฐ๋ ๊ฐ์ ธ์์ ์ด๋ค.

### 4. Inner Join
FROM ์ ์ ๋ฐ์ดํฐ์ JOIN ์ ์ ๋ฐ์ดํฐ๋ฅผ JOIN ์กฐ๊ฑด์ ๊ธฐ์ค์ผ๋ก ์๋ก ์ฐ๊ฒฐํ๋ ๊ฒ์ด๋ค. (๋ ํ์ด๋ธ์ ๊ต์งํฉ์ด๋ค)

### 5. SQL ์ฟผ๋ฆฌ๊ฐ ์คํ๋๋ ์์
```java
select u.name, count(u.name) as count_name from orders o
inner join users u
on o.user_id = u.user_id 
where u.email like '%naver.com'
group by u.name
```
์ ์ฟผ๋ฆฌ๊ฐ ์คํ๋๋ ์์: from โ join โ where โ group by โ select
```java
select c1.title, c2.week, count(*) as cnt from courses c1
inner join checkins c2 on c1.course_id = c2.course_id
 inner join orders o on c2.user_id = o.user_id
where o.created_at >= '2020-08-01'
group by c1.title, c2.week
order by c1.title, c2.week
```
`inner join`์ ์ฌ๋ฌ ๊ฐ ์ฐ๊ฒฐํ  ์ ์๋ค. 
`group by`, `order by` ๋ํ ์ฝค๋ง๋ฅผ ์ด์ฉํด์ ๋ ๊ทธ๋ฃนํํ๊ฑฐ๋ ์ ๋ ฌํ  ์ ์๋ค.
`count`๋ NULL๊ฐ์ ์๋์ผ๋ก ์ ์ธํ๊ณ  ๊ฐฏ์๋ฅผ ์ธ์ด์ค๋ค.

## ๐ง Union
ํ๋๊ฐ ๋ค ๋๊ฐ์๋ฐ, ํ๋๋ 7์๋ฌ ๊ฑฐ ํ๋๋ 8์๋ฌ ๊ฑฐ.. ๋ถ์ฌ์ ํ ๋ฒ์ ๋ณด๊ณ  ์ถ์ ๋? `union all`
```java
(
	select '7์' as month, c.title, c2.week, count(*) as cnt from checkins c2
	inner join courses c on c2.course_id = c.course_id
	inner join orders o on o.user_id = c2.user_id
	where o.created_at < '2020-08-01'
	group by c2.course_id, c2.week
    order by c2.course_id, c2.week -> ์ ์ฉ ์๋จ
)
union all
(
	select '8์' as month, c.title, c2.week, count(*) as cnt from checkins c2
	inner join courses c on c2.course_id = c.course_id
	inner join orders o on o.user_id = c2.user_id
	where o.created_at > '2020-08-01'
	group by c2.course_id, c2.week
    order by c2.course_id, c2.week -> ์ ์ฉ ์๋จ
)
```
union ์์์๋ order by๊ฐ ์ ์ฉ๋์ง ์๋๋ค. ์ด ๊ฒ์ sub query๋ก ํด๊ฒฐํ  ์ ์๋ค.


---


## ๐ ์ฟผ๋ฆฌ ์์ฑ๋ฒ
1) show tables๋ก ์ด๋ค ํ์ด๋ธ์ด ์๋์ง ์ดํด๋ณด๊ธฐ
2) ์ ์ผ ์ํ๋ ์ ๋ณด๊ฐ ์์ ๊ฒ ๊ฐ์ ํ์ด๋ธ์ select * from ํ์ด๋ธ๋ช limit 10 ์ฟผ๋ฆฌ ๋ ๋ ค๋ณด๊ธฐ
3) ์ํ๋ ์ ๋ณด๊ฐ ์์ผ๋ฉด ๋ค๋ฅธ ํ์ด๋ธ์๋ 2)๋ฅผ ํด๋ณด๊ธฐ
4) ํ์ด๋ธ์ ์ฐพ์๋ค! ๋ฒ์ฃผ๋ฅผ ๋๋ ์ ๋ณด๊ณ ์ถ์ ํ๋๋ฅผ ์ฐพ๊ธฐ
5) ๋ฒ์ฃผ๋ณ๋ก ํต๊ณ๋ฅผ ๋ณด๊ณ ์ถ์ ํ๋๋ฅผ ์ฐพ๊ธฐ
6) SQL ์ฟผ๋ฆฌ ์์ฑํ๊ธฐ!

---

## โจ Subquery
์๋ธ์ฟผ๋ฆฌ๋, ์ฟผ๋ฆฌ์์ ์ฟผ๋ฆฌ๋ผ๋ ์๋ฏธ!
ํ์์ฟผ๋ฆฌ์ ๊ฒฐ๊ณผ๋ฅผ ์์ ์ฟผ๋ฆฌ ์์์ ์ฌ์ฉํ๋ฉด, SQL ์ฟผ๋ฆฌ๊ฐ ํจ์ฌ ๊ฐ๋จํด์ง๋ค.
Subquery๋ฅผ ์ฌ์ฉํ์ง ์์๋ ์ํ๋ ๋ฐ์ดํฐ๋ฅผ ์ป์ด๋ผ ์ ์๊ฒ ์ง๋ง, ๋ ํธํ๊ณ  ๊ฐ๋จํ๊ฒ ์ํ๋ ๋ฐ์ดํฐ๋ฅผ ์ป๊ธฐ ์ํด ์ฌ์ฉ๋๋ ๊ธฐ๋ฅ์ด๋ค.
```sql
select u.user_id, u.name, u.email from users u
inner join orders o on u.user_id = o.user_id
where o.payment_method = 'kakaopay'
```

```sql
select u.user_id, u.name, u.email from users u
where u.user_id in (
	select user_id from orders
	where payment_method = 'kakaopay'
)
```
### 1. where
where ํ๋๋ช in (subquery)
(1) from ์คํ
(2) Subquery ์คํ
(3) where .. in ์ ์์ subquery์ ๊ฒฐ๊ณผ์ ํด๋น๋๋ ์กฐ๊ฑด์ผ๋ก ํํฐ๋ง ํด์ค
(4) ์กฐ๊ฑด์ ๋ง๋ ๊ฒฐ๊ณผ ์ถ๋ ฅ

### 2. select
select ํ๋๋ช, ํ๋๋ช, (subquery) from .. 
(1) ๋ฐ์ select * from ๋ฌธ์์ ๋ฐ์ดํฐ๋ฅผ ํ์คํ์ค ์ถ๋ ฅํ๋ ๊ณผ์ ์์
(2) select ์์ subquery๊ฐ ๋งค ๋ฐ์ดํฐ ํ์ค๋ง๋ค ์คํ๋๋๋ฐ
(3) ๊ทธ ๋ฐ์ดํฐ ํ ์ค์ ์กฐ๊ฑด์ ๊ฐ๋ ๋ฐ์ดํฐ์ ๊ฐ์ subquery์์ ๊ณ์ฐํด์
(4) ํจ๊ป ์ถ๋ ฅํด์ค๋ค!

### 3. from
๊ฐ์ฅ ๋ง์ด ์ฌ์ฉ๋๋ ์ ํ์ด๋ค.
๋ด๊ฐ ๋ง๋  Select์ ์ด๋ฏธ ์๋ table์ Joinํ๊ณ  ์ถ์ ๋ ์ฌ์ฉํ  ์ ์๋ค.
(1) ๋จผ์  ์๋ธ์ฟผ๋ฆฌ์ select๊ฐ ์คํ๋๊ณ ,
(2) ์ด๊ฒ์ ํ์ด๋ธ์ฒ๋ผ ์ฌ๊ธฐ๊ณ  ๋ฐ์ select๊ฐ ์คํ!

```sql
select pu.user_id, a.avg_like, pu.point from point_users pu
inner join (
	select user_id, round(avg(likes),1) as avg_like from checkins
	group by user_id
) a on pu.user_id = a.user_id
```

### 4. with์ 
```sql
select c.title,
       a.cnt_checkins,
       b.cnt_total,
       (a.cnt_checkins/b.cnt_total) as ratio
from
(
	select course_id, count(distinct(user_id)) as cnt_checkins from checkins
	group by course_id
) a
inner join
(
	select course_id, count(*) as cnt_total from orders
	group by course_id 
) b on a.course_id = b.course_id
inner join courses c on a.course_id = c.course_id
```
```sql
with table1 as (
	select course_id, count(distinct(user_id)) as cnt_checkins from checkins
	group by course_id
), table2 as (
	select course_id, count(*) as cnt_total from orders
	group by course_id
)
select c.title,
       a.cnt_checkins,
       b.cnt_total,
       (a.cnt_checkins/b.cnt_total) as ratio
from table1 a inner join table2 b on a.course_id = b.course_id
inner join courses c on a.course_id = c.course_id
```

<br>
<br>

---

## โจ ๋ฌธ์์ด 
### 1.SUBSTRING_INDEX : email์์ ์์ด๋๋ง ๊ฐ์ ธ์ค๊ธฐ
```sql
select user_id, email, SUBSTRING_INDEX(email, '@', 1) from users
```
```sql
select user_id, email, SUBSTRING_INDEX(email, '@', -1) from users
```
`1`์ผ ๋ : ์์ด๋๋ง ๊ฐ์ ธ์์ง
`-1`์ผ ๋ : ๋๋ฉ์ธ๋ง ๊ฐ์ ธ์์ง
@๋ฅผ ๊ธฐ์ค์ผ๋ก ํ์คํธ๋ฅผ ์ชผ๊ฐ๊ณ , ๊ทธ ์ค ์ฒซ๋ฒ์งธ ์กฐ๊ฐ์ ๊ฐ์ ธ์๋ผ ๋ผ๋ ์๋ฏธ์ด๋ค!

### 2. SUBSTRING : ~์ด๋๊น์ง๋ง ๊ฐ์ ธ์ค์
```sql
select order_no, created_at, substring(created_at,1,10) as date from orders
```
`substring(field,i,j)` : field์์ ๋ฌธ์์ด์ i๋ฒ์งธ๋ถํฐ j๊ฐ ๊น์ง

<br>
<br>

---


## โจ CASE๋ฌธ
```sql
select pu.point_user_id, pu.point,
case 
when pu.point > 10000 then '์ ํ๊ณ  ์์ด์!'
else '์กฐ๊ธ ๋ ๋ฌ๋ ค์ฃผ์ธ์!'
END as '๊ตฌ๋ถ'
from point_users pu;
```
subquery๋ฅผ ์ด์ฉํ๋ฉด case๋ฌธ์ผ๋ก ํต๊ณ๋ฅผ ๋ผ ์ ์๋ค.
```sql
select level, count(*) as cnt from (
	select pu.point_user_id, pu.point,
	case 
	when pu.point > 10000 then '1๋ง ์ด์'
	when pu.point > 5000 then '5์ฒ ์ด์'
	else '5์ฒ ๋ฏธ๋ง'
	END as lv
	from point_users pu
) a
group by lv
```
```sql
with table1 as (
	select pu.point_user_id, pu.point,
	case 
	when pu.point > 10000 then '1๋ง ์ด์'
	when pu.point > 5000 then '5์ฒ ์ด์'
	else '5์ฒ ๋ฏธ๋ง'
	END as lv
	from point_users pu
)
select lv, count(*) as cnt from table1
group by lv
```

## ๐ Reference
[SQL](https://terms.naver.com/entry.naver?docId=2270454&cid=51173&categoryId=51173)
[Query](https://terms.naver.com/entry.naver?docId=834420&cid=42344&categoryId=42344)
[cloudstudying.kr](https://cloudstudying.kr/lectures/502)
[ [Table Join -  INNER JOIN /  ์ค์ต]|์์ฑ์ ์ง๋ชจ](https://blog.naver.com/zigzagzymo/222885387145)

