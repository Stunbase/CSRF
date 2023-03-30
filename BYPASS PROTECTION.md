CREATE TABLE personnes (
    id INT PRIMARY KEY,
    nom VARCHAR(50),
    date_de_naissance DATE,
    age INT GENERATED ALWAYS AS (YEAR(CURDATE()) - YEAR(date_de_naissance) - (DATE_FORMAT(CURDATE(), '%m%d') < DATE_FORMAT(date_de_naissance, '%m%d')))
);


