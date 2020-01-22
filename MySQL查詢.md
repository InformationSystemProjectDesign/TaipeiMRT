# 加入行程

##  INSERT INTO dtbse.schedule VALUE ('S00001','10556001@ntub.edu.tw','My 1日遊','2019-11-27');

## INSERT INTO dtbse.schedule_route VALUE ('R00001','S00001','1','BR13','R');
## INSERT INTO dtbse.schedule_route VALUE ('R00002','S00001','2','BR10','T');
## INSERT INTO dtbse.schedule_route VALUE ('R00003','S00001','3','BL15','R');
## INSERT INTO dtbse.schedule_route VALUE ('R00004','S00001','4','BL13','');

## INSERT INTO dtbse.schedule_route_detail (schedule_route_id,detail_array,food_id) VALUES ('R00004',1,'F00002');
## INSERT INTO dtbse.schedule_route_detail (schedule_route_id,detail_array,att_id) VALUES ('R00004',2,'A00001');


# 查詢行程

## SELECT CONCAT(sta_name,' ',b.sta_id) as station,food_name,att_name FROM dtbse.schedule AS a
## JOIN dtbse.schedule_route AS b ON a.schedule_id = b.schedule_id
## LEFT JOIN dtbse.schedule_route_detail AS c ON b.schedule_route_id = c.schedule_route_id
## JOIN dtbse.station As d on b.sta_id = d.sta_id
## LEFT JOIN dtbse.food As e on c.food_id = e.food_id
## LEFT JOIN dtbse.attractions As f on c.att_id = f.att_id
## WHERE a.schedule_id = 'S00001'
## ORDER BY schedule_route_array,detail_array;

# 刪除行程

## SET SQL_SAFE_UPDATES=0;
## DELETE FROM dtbse.schedule_route_detail
## WHERE schedule_route_id IN (SELECT * FROM (SELECT a.schedule_route_id FROM dtbse.schedule_route_detail AS a
## JOIN dtbse.schedule_route AS b ON a.schedule_route_id = b.schedule_route_id
## WHERE schedule_id = 'S00001') AS c);

## DELETE FROM dtbse.schedule_route
### WHERE schedule_id = 'S00001';

## DELETE FROM dtbse.schedule
## WHERE schedule_id = 'S00001';		

		   
