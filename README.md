# TEST2
--CREATING TABLES--
create table products(
product_id int,
product_name varchar (100),
description varchar (100),
price money not null,
type_id int not null
);

create table type_of_products(
type_id int not null,
name varchar (100)
);

create table buyers(
buyer_id int,
buyer_name varchar (100),
birthday date
);

create table orders(
order_id int,
buyer_id int,
order_number int not null,
order_date datetime,
order_summa money not null
);

create table relations(
order_id int not null,
product_id int not null,
);
--INSERT VALUES--
insert into buyers(buyer_id,buyer_name,birthday)
			values (753, 'Curakurakova', '1998.04.12'),
		   (832, 'Glebova', '1993.07.16'),
		   (991, 'Bravencova', '2001.10.28'),
		   (1028, 'John Smith', '2000.05.03'),
		   (1109, 'Atazhanov', '1986.10.12'),
		   (1177, 'Zavadil', '2003.06.11'),
		   (1201, 'Smith', '1980.09.27');
       
insert into orders (order_id, buyer_id, order_number, order_date, order_summa)
	values (1459, 1201, 151, '20200402', 12750),
		   (1567, 991, 259, '20200417', 6700),
		   (1615, 832, 307, '20200502', 21440),
		   (1646, 1109, 338, '20200507', 15540),
		   (1660, 1201, 352, '20200516', 2100),
		   (1708, 832, 400, '20200521', 6700),
		   (1718, 1028, 410, '20200521', 12300),
		   (1893, 832, 115, '20200611', 4600),
		   (1923, 1109, 85, '20200629', 23990),
		   (1959, 1201, 151, '20200702', 1300),
		   (2052, 832, 244, '20200730', 7900),
		   (2057, 991, 249, '20200730', 16900),
		   (2106, 753, 298, '20200808', 900),
		   (2146, 1201, 338, '20200815', 2200),
		   (2181, 832, 373, '20200823', 16740);
       
insert into type_of_products(type_id, name)
	values (1, 'Physical'),
		   (2, 'Digital');
       
insert into products (product_id, product_name, description, price, type_id)
	valuies (16, 'Processor V5', '4-core processor, 3600 MHz', 12300, 1),
		   (29, 'Motherboard R7Q', '2 slots DDR4, 1 slot PCI-E', 4600, 1),
		   (38, 'Keyboard S939', 'Wired, interface USB', 1300, 1),
		   (47, 'Mouse N56', 'USB', 900, 1),
		   (60, 'Motherboard ES20', '4 slots DDR4, 2 slots PCI-E', 6700, 1),
		   (71, 'Printer 3075', 'Laser, 20 page/min (A4), USB', 3500, 1),
		   (83, 'CPU cooler D17', NULL, 450, 1),
		   (96, 'CPU V7', '6-core CPU, 3700 MHz', 15540, 1),
		   (108, 'Antivirus software', NULL, 1200, 2),
		   (125, 'Operation system', NULL, 6700, 2);
		   
insert into relations(order_id, product_id)
	values (1459, 16), (1459, 83), (1567, 125), (1615, 29),
		   (1615, 96), (1615, 38), (1646, 96), (1660, 108),
		   (1660, 47), (1708, 60), (1718, 16), (1893, 29),
		   (1923, 60), (1923, 83), (1923, 96), (1923, 38),
		   (1959, 38), (2052, 108), (2052, 125), (2057, 16),
		   (2057, 29), (2106, 47), (2146, 38), (2146, 47),
		   (2181, 108), (2181, 96);
