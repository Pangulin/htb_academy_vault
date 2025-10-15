first we need to find the number of collumns in the table wich is beeing returned to us. (some collums might be hidden)

we can do this once again by using junk data
in this case i used null as junk data 

to start out we looked for a way to break the query be injecting certain symbols like: 
" ' ) or a combination of those. 

Once we found a way to break the query we can start injecting 

to test for the amount of collumns we start by injection the null values like this: 

<span style="color:rgb(255, 0, 0)">'union select null-- -</span> 

we also comment out the end to avoid any other logic from beeing executed 

finally we end up with something like this wich returns something: 

<span style="color:rgb(255, 0, 0)">
'union select null,null,null,null-- -</span>

therefore the table has 4 collumns  

[%27union select username || '-' || password from users-- -]

to get 2 collumn results within 1 collumn 