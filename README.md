/*1.*/
CREATE VIEW vw_idioma as
SELECT i.idioma_id, nome, filme_id, titulo
FROM idioma i, filme f
WHERE i.idioma_id = f.idioma_id;

SELECT * FROM vw_idioma;
/*2.*/
CREATE VIEW vw_inventario as
SELECT i.inventario_id, aluguel_id, l.loja_id
FROM inventario i, loja l, aluguel a
WHERE i.inventario_id = a.inventario_id and i.loja_id = l.loja_id;

SELECT * FROM vw_inventario;
/*3.*/
CREATE VIEW vw_aluguel as
SELECT aluguel_id, data_de_aluguel, a.cliente_id, primeiro_nome, email
FROM aluguel a, cliente c
WHERE a.cliente_id = c.cliente_id 
ORDER BY primeiro_nome asc;

SELECT * FROM vw_aluguel


/*Exercícios de sp*/
/*1.*/
DELIMITER //
CREATE PROCEDURE sp_pais_id (in id int)
BEGIN
	SELECT * FROM pais
    WHERE pais_id = id;
    END //
DELIMITER ;

CALL sp_pais_id(8)
/*2.*/
DELIMITER //
CREATE PROCEDURE sp_aluguel_id (in id int)
BEGIN
	SELECT * FROM aluguel
    WHERE aluguel_id = id;
    END //
DELIMITER ;

CALL sp_aluguel_id(4)

/*3.*/
DELIMITER //
CREATE PROCEDURE sp_ator_id (in id int)
BEGIN
	SELECT * FROM ator
    WHERE ator_id = id;
    END //
DELIMITER ;

CALL sp_ator_id(105)

