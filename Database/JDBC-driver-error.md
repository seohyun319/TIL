### 에러

JDBC DRIVER road probcom.mysql.jdbc.Driver
java.lang.ClassNotFoundException: com.mysql.jdbc.Driver
at java.base/jdk.internal.loader.BuiltinClassLoader.loadClass(BuiltinClassLoader.java:606)
at java.base/jdk.internal.loader.ClassLoaders$AppClassLoader.loadClass(ClassLoaders.java:168)
at java.base/java.lang.ClassLoader.loadClass(ClassLoader.java:522)
at java.base/java.lang.Class.forName0(Native Method)
at java.base/java.lang.Class.forName(Class.java:377)
at SQLtest.main(SQLtest.java:12)
connection errNo suitable driver found for jdbc:mysql://localhost:3307/roomescape_review_project
java.sql.SQLException: No suitable driver found for jdbc:mysql://localhost:3307/roomescape_review_project
at java.sql/java.sql.DriverManager.getConnection(DriverManager.java:702)
at java.sql/java.sql.DriverManager.getConnection(DriverManager.java:228)
at SQLtest.main(SQLtest.java:20)
오후 3:45:03: Task execution finished 'SQLtest.main()'.

### 원인

드라이버를 못 찾는다...

### 해결법

build.gradle의 dependencies에 `implementation group: 'mysql', name: 'mysql-connector-java', version: '8.0.29'` 추가
