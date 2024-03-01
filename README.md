# Funcion_SQL
DELIMITER $$
CREATE FUNCTION puntuarlugar(nombrec VARCHAR(40), calif INT, usuce INT)
RETURNS VARCHAR(100)
DETERMINISTIC
BEGIN 
	DECLARE rta VARCHAR(100);
		 INSERT INTO recomendaciones (nombre_lugar, calificacion_lugar, id_usuario) 
         VALUES (nombrec, calif, usuce);
	IF calif = 1 OR 2 THEN 
    SET rta ="Sitio no recomendado.";
    ELSEIF calif = 4 OR 5 THEN 
    SET rta ="Sitio recomendado";
    ELSEIF calif = 3 THEN 
    SET rta="Sitio promedio";
    ELSE 
		SET rta="Recomendacion invalida";
		END IF;
        RETURN rta; 
END;	
$$
