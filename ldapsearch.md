```
yum -y install openldap-clients

可能需要配置
cat /etc/openldap/ldap.conf 
BASE    ou=People,dc=broada,dc=com
URI     ldap://10.1.2.245/
binddn uid=ldapaccessor,ou=People,dc=broada,dc=com
bindpw uvBbmKZCig2Kiw7
TLS_CACERTDIR   /etc/openldap/certs
SASL_NOCANON    on

ldapsearch -x -Z -H ldap://10.1.2.245 -b 'ou=People,dc=broada,dc=com' -w uvBbmKZCig2Kiw7 -D "uid=ldapaccessor,ou=People,dc=broada,dc=com"

```
