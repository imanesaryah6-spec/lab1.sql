# lab1.sql
@@ -1,112 +1,55 @@
-- ============================================================
-- Customized MySQL Lab Reference (Different Database & Names)
-- Safe for repository submission
-- ============================================================

-- ------------------------------------------------------------
-- 1. Database Creation & Selection
-- ------------------------------------------------------------
CREATE DATABASE IF NOT EXISTS store_db
    CHARACTER SET utf8mb4
    COLLATE utf8mb4_unicode_ci;

USE store_db;

SHOW DATABASES;


-- ------------------------------------------------------------
-- 2. Table Creation (Custom Structure)
-- ------------------------------------------------------------
CREATE TABLE IF NOT EXISTS members (
    id INT AUTO_INCREMENT PRIMARY KEY,
    full_name VARCHAR(50) NOT NULL,
    email VARCHAR(100) NOT NULL UNIQUE
) ENGINE=InnoDB;


-- ------------------------------------------------------------
-- 3. Data Insertion & Selection
-- ------------------------------------------------------------
INSERT INTO clients_data (full_name, email) VALUES
('Omar Mansouri', 'omar@store.com'),
('Khadija Chraibi', 'khadija@store.com'),
('Amine Bennani', 'amine@test.net');

SELECT * FROM members;
SELECT full_name, email FROM members WHERE email LIKE '%@store.com';
SELECT COUNT(*) AS total_members FROM members;
SELECT full_name, email FROM members ORDER BY full_name ASC;
SELECT full_name, email FROM members ORDER BY id DESC LIMIT 2;


-- ------------------------------------------------------------
-- 4. Updates & Deletions
-- ------------------------------------------------------------
UPDATE members
SET email = 'khadija.bennani@store.com'
WHERE full_name = 'Khadija Chraibi';

DELETE FROM members
WHERE full_name = 'Amine Bennani';


-- ------------------------------------------------------------
-- 5. Transactions & Rollback
-- ------------------------------------------------------------
START TRANSACTION;

DELETE FROM members WHERE full_name = 'Omar Mansouri';

-- Undo changes:
ROLLBACK;

-- Save changes:
-- COMMIT;


-- ------------------------------------------------------------
-- 6. Index Management & Execution Plan
-- ------------------------------------------------------------
CREATE INDEX idx_member_email ON members(email);

SHOW INDEX FROM members;

EXPLAIN SELECT * FROM members WHERE email = 'omar@store.com';

DROP INDEX idx_member_email ON members;


-- ------------------------------------------------------------
-- 7. User Management & Grants
-- ------------------------------------------------------------
CREATE USER 'store_admin'@'localhost' IDENTIFIED BY 'CustomPass2026!';

GRANT SELECT, INSERT, UPDATE, DELETE ON store_db.* TO 'store_admin'@'localhost';

FLUSH PRIVILEGES;

SHOW GRANTS FOR 'store_admin'@'localhost';

-- DROP USER 'store_admin'@'localhost';

-- MySQL dump 10.13  Distrib 8.0.46, for Win64 (x86_64)
--
-- Host: localhost    Database: etudiant
-- ------------------------------------------------------
-- Server version	8.0.46

/*!40101 SET @OLD_CHARACTER_SET_CLIENT=@@CHARACTER_SET_CLIENT */;
/*!40101 SET @OLD_CHARACTER_SET_RESULTS=@@CHARACTER_SET_RESULTS */;
/*!40101 SET @OLD_COLLATION_CONNECTION=@@COLLATION_CONNECTION */;
/*!50503 SET NAMES utf8mb4 */;
/*!40103 SET @OLD_TIME_ZONE=@@TIME_ZONE */;
/*!40103 SET TIME_ZONE='+00:00' */;
/*!40014 SET @OLD_UNIQUE_CHECKS=@@UNIQUE_CHECKS, UNIQUE_CHECKS=0 */;
/*!40014 SET @OLD_FOREIGN_KEY_CHECKS=@@FOREIGN_KEY_CHECKS, FOREIGN_KEY_CHECKS=0 */;
/*!40101 SET @OLD_SQL_MODE=@@SQL_MODE, SQL_MODE='NO_AUTO_VALUE_ON_ZERO' */;
/*!40111 SET @OLD_SQL_NOTES=@@SQL_NOTES, SQL_NOTES=0 */;

-- ------------------------------------------------------------
-- 8. Cleanup Statements
-- ------------------------------------------------------------
-- DROP TABLE members;
-- DROP DATABASE store_db;
-- EXIT;
--
-- Table structure for table `eleve`
--

DROP TABLE IF EXISTS `eleve`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `eleve` (
  `id` int NOT NULL AUTO_INCREMENT,
  `nom` varchar(100) DEFAULT NULL,
  `email` varchar(100) DEFAULT NULL,
  PRIMARY KEY (`id`),
  UNIQUE KEY `email` (`email`),
  KEY `idx_email` (`email`)
) ENGINE=InnoDB AUTO_INCREMENT=4 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

-- ------------------------------------------------------------
-- 9. Terminal Export & Import Commands (Execute in Terminal)
-- ------------------------------------------------------------
-- Export single table:
--   mysqldump -u root -p store_db members > members_backup.sql
--
-- Export entire database with options:
--   mysqldump -u root -p --single-transaction --routines --triggers store_db > store_db_full.sql
-- Dumping data for table `eleve`
--
-- Import/Restore backup:
--   mysql -u root -p store_db < members_backup.sql

LOCK TABLES `eleve` WRITE;
/*!40000 ALTER TABLE `eleve` DISABLE KEYS */;
INSERT INTO `eleve` VALUES (1,'Imane','bououalaimane@gmail.com'),(3,'Youssef','youssefbounouala123@gmail.com');
/*!40000 ALTER TABLE `eleve` ENABLE KEYS */;
UNLOCK TABLES;
/*!40103 SET TIME_ZONE=@OLD_TIME_ZONE */;

/*!40101 SET SQL_MODE=@OLD_SQL_MODE */;
/*!40014 SET FOREIGN_KEY_CHECKS=@OLD_FOREIGN_KEY_CHECKS */;
/*!40014 SET UNIQUE_CHECKS=@OLD_UNIQUE_CHECKS */;
/*!40101 SET CHARACTER_SET_CLIENT=@OLD_CHARACTER_SET_CLIENT */;
/*!40101 SET CHARACTER_SET_RESULTS=@OLD_CHARACTER_SET_RESULTS */;
/*!40101 SET COLLATION_CONNECTION=@OLD_COLLATION_CONNECTION */;
/*!40111 SET SQL_NOTES=@OLD_SQL_NOTES */;

-- Dump completed on 2026-11-01  0:19:26
