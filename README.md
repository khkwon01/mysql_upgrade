# mysql_upgrade

## 1. Major changes of MySQL 8.0 compared to previous version
(삭제된 feature : https://dev.mysql.com/doc/refman/8.0/en/mysql-nutshell.html#mysql-nutshell-removals)
- Account
    - 계정 생성할 때 create user 구문 사용
    - identified by password 구문 제거, set password = password('auth_string')도 제거
    - cache가 적용된 SHA256 인증 방식 사용 (8.0 이전까지 mysql_native_password 방식 사용)
      - MySQL 8.0 이전 client를 사용시 오류가 발생하면 아래 옵션 추가(임시적 사용후 변경권장)
        - default_authentication_plugin=mysql_native_password (mysqld)
