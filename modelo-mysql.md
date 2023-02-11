CREATE DATABASE manufatura;

USE manufatura;

SET SQL_SAFE_UPDATES = 0;

CREATE TABLE ordem (
	codigo varchar(20) primary key,
	componente varchar(15),
    quantidade int,
    status varchar(20),
    temperatura varchar(20),
    pressao varchar(20),
    velocidade varchar(20)
);

CREATE TABLE maquina (
	id_maquina char(1) primary key
);

CREATE TABLE produz (
	codigo varchar(20),
    id_maquina char(1),
    t_inicio datetime,
    t_fim datetime,
    FOREIGN KEY (codigo) REFERENCES ordem(codigo),
    FOREIGN KEY (id_maquina) REFERENCES maquina(id_maquina)
);	

CREATE TABLE configura (
	codigo varchar(20),
    id_maquina varchar(20),
    FOREIGN KEY (codigo) REFERENCES ordem(codigo),
    FOREIGN KEY (id_maquina) REFERENCES maquina(id_maquina)
);

INSERT INTO maquina(id_maquina) VALUES ("A");
INSERT INTO maquina(id_maquina) VALUES ("B");