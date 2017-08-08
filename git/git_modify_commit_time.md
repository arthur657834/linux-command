```shell
#!/bin/bash
rm -rf "$(git rev-parse --git-dir)/refs/original/"

commit="$1"
date=$(date -d "$2" +%s)
git filter-branch --env-filter \
    "if [ \$GIT_COMMIT = '$commit' ]; then
         export GIT_AUTHOR_DATE='$date'
         export GIT_COMMITTER_DATE='$date'
         export GIT_COMMITTER_NAME="\$GIT_AUTHOR_NAME"
         export GIT_COMMITTER_EMAIL="\$GIT_AUTHOR_EMAIL"
     fi"
```

使用:
1. git log 得到想要修改对commit对应的hash code
2. sh modify.sh db124212db761c3df5b366b8f0480b07471c354b "2017-05-06 10:0:0"  时间为你想要修改的时间
3. git push

tips:
git 在算 hash 的時候，也會包含 parent 的 commit id ，所以 parent 的 commit id 變了，所有的 child commit id 都會跟著變，這個在寫 script 批次處理的時候需要注意一下。


