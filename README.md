![alt text](image.png)


create database cine;
use cine;


create table pelicula(
  id int not null auto_increment,
  titulo varchar(50) not null,
  genero_fk varchar(50) not null,
  duracion varchar(50) not null,
  clasificacion varchar(50) not null,
  sala_fk varchar(50) not null,
  fecha varchar(50) not null
  hora varchar(50) not null,
  primary key(id),
  foreign key(sala_fk) references sala(id),
  foreign key(genero_fk) references genero(id)
);
insert into pelicula (titulo,genero,duracion,clasificacion,sala,fecha,hora) values('inception','PG-13','140min','1','');

create table sala(
  id int not null auto_increment,
  n_sala varchar(50) not null,
  capacidad varchar(50) not null,
  primary key(id)
);
insert into _ () values();

create table genero(
  id int not null auto_increment,
  n_genero varchar(50) not null,
  primary key(id)
);
insert into _ () values();

create table cliente(
  id int not null auto_increment,
  nombre varchar(50) not null,
  correo varchar(50) not null,
  telefono varchar(50) not null,
  forma_pago_fk varchar(50) not null,
  monto varchar(50) not null,
  primary key(id),
  foreign key(forma_pago_fk) references forma_pago(id)
);
insert into _ () values();

create table forma_pago(
  id int not null auto_increment,
  forma varchar(50) not null,
  primary key (id)
);
insert into _ () values();

create table detalle_venta(
  id int not null auto_increment,
  cliente_fk varchar(50) not null,
  pelicula_fk varchar(50) not null,
  forma_pago_fk varchar(50) not null,
  monto_fk varchar(50) not null,
  sala_fk varchar(50) not null,
  fecha_fk varchar(50) not null
  hora_fk varchar(50) not null
  primary key(id),
  foreign key(cliente_fk) references cliente(id),
  foreign key(forma_pago_fk) references cliente(id),
  foreign key(monto_fk) references cliente(id),
  foreign key(sala_fk) references pelicula(id),
  foreign key(pelicula_fk) references pelicula(id),
  foreign key(fecha_fk) references pelicula(id),
  foreign key(hora_fk) references pelicula(id)
);