# nagios

Collection of Nagios plugins for EOS.

#### To-DO

* Allow for check_fork function to read hosts from file.


####  📌 check_bp.py


A python script to monitor your Block Producers using nagios or other.
Each function performs a particular action and EXITS with 0 if there are no issues and EXITS with 2 if there are issues. 



#####  (1) Check the participation rate of your block producer 

* Checks your host has a participation rate of more than 0.5.
* EXITS with 0 if participation rate > 5.
* EXITS with 2 if participation rate < 5.

###### Usage for check_ratio
`check_bp.py  x.x.x.x:8888 check_ratio`



#####  (2) Check the head_block_num of your producer is incrementing 

* Checks your host's head_block_num and saves that as a varaible, waits 5 secodns and checks again.
* EXITS with 0 if head_block_num has incremented. 
* EXITS with 2 if head_block_num has not incremented. 

###### Usage for check_head
`check_bp.py  x.x.x.x:8888 check_head`



#####  (3) Check multiple hosts and saves the head_block_num, take the median average and checks against your host.

* Check multiple hosts and saves the head_block_num, takes the median average. If any hosts are  
* EXITS with 0 if head_block_num has incremented. 
* EXITS with 2 if head_block_num difference is out of bounds(> abs(5) of average)

###### Usage for check_fork
`check_bp.py  x.x.x.x:8888 check_fork`


