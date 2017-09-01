```
yum -y install getmail
useradd getmailtest
echo "123456" | passwd --stdin getmailtest

su getmailtest
mkdir ~/.getmail
cd ~/.getmail
mkdir new cur tmp
touch log getmailrc

vi getmailrc
[options]

verbose = 0

delete = true

read_all = false

message_log = ~/.getmail/log

message_log_verbose = true

[retriever]

type = SimplePOP3Retriever

server = mail.broada.com

username = gittag

password = y8nKBtrkVBJjbzF

[destination]

type = Maildir

path = ~/.getmail/

getmail --rcfile=getmailrc
```
