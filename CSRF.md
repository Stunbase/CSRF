CREATE TABLE personnes (
    id INT PRIMARY KEY,
    nom VARCHAR(50),
    date_de_naissance DATE,
    age INT GENERATED ALWAYS AS (YEAR(CURRENT_DATE()) - YEAR(date_de_naissance) - (DATE_FORMAT(CURRENT_DATE(), '%m%d') < DATE_FORMAT(date_de_naissance, '%m%d'))) VIRTUAL,
    CONSTRAINT chk_date CHECK (date_de_naissance <= CURRENT_DATE())
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci
ALLOW_INVALID_DATES;
