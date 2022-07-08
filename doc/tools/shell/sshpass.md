# sshpass

```shell
sshpass -p "password" scp -r user@example.com:/some/remote/path /some/local/path
```

```shell
sshpass -f "/path/to/passwordfile" scp -r user@example.com:/some/remote/path /some/local/path
```


replacement of sshpass:

For example create 'test.exp' :

```shell
#!/usr/bin/expect
        spawn scp  /usr/bin/file.txt root@<ServerLocation>:/home
        set pass "Your_Password"
        expect {
        password: {send "$pass\r"; exp_continue}
                  }
```
run the script

```shell
expect test.exp 
```
