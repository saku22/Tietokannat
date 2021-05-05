# Tietokannat
### Tehtävä 1  
Omalla nimelläni löytyy kauan sitten kastettuja mm. 1688. Myös nimeni muunnoksia on Sakuds, Sakuas, Sakuis.  
Matti nimellä löytyy taas hyvin vanhoja kastoja 1700 ja 1800-luvulta.  
Maija nimellä löytyy paljon tuloksia ja moni niistä on taas nimimuunnoksia esimerkiksi Maija -> Maja.
### Tehtävä 2
Olen syöttänyt varmaan satoihin palveluihin sähköpostiosoitteeni.
### Tehtävä 3
![Kuva](OpettajaKurssit.png)
### Tehtävä 4
SELECT * FROM Kurssisuoritus
### Tehtävä 5
SELECT kurssi FROM Kurssisuoritus
### Tehtävä 6
SELECT DISTINCT kurssi FROM Kurssisuoritus
### Tehtävä 7
SELECT * FROM Opiskelija WHERE nimi = 'Anna'
### Tehtävä 8
Select * FROM Kurssisuoritus WHERE Opiskelija = 'Pihla'
### Tehtävä 9
SELECT * FROM Opiskelija WHERE pääaine LIKE '%tiede%' 
SELECT DISTINCT pääaine FROM Opiskelija WHERE pääaine LIKE '%tiede%'
### Tehtävä 10  
SELECT Kurssi.nimi. Kurssisuoritus.päivämäärä. Kurssisuoritus.arvosana FROM Kurssi, Kurssisuoritus  
WHERE Kurssi.kurssitunnus = Kurssisuoritus.kurssi
### Tehtävä 11  
SELECT Opiskelija.nimi, Kurssisuoritus.päivämäärä, Kurssisuoritus.arvosana FROM Opiskelija, Kurssisuoritus 
### Tehtävä 12
SELECT Kurssi.nimi AS kurssi, Tehtävä.nimi AS tehtävä  
FROM Kurssi, Tehtävä, Kurssitehtävä  
WHERE Kurssi.Kurssitunnus = Kurssitehtävä.kurssi  
AND Tehtävä.tunnus = Kurssitehtävä.tehtävä
### Tehtävä 13
SELECT Kurssi.nimi AS Kurssin_nimi, Tehtävä.nimi AS Tehtävän_nimi  
FROM Kurssi, Tehtävä, Kurssitehtävä, Opiskelija, Tehtäväsuoritus  
WHERE Opiskelija.nimi = 'Anna'  
AND Kurssi.kurssitunnus = Kurssitehtävä.kurssi  
AND Tehtävä.tunnus = Kurssitehtävä.tehtävä  
AND Kurssitehtävä.tunnus = Tehtäväsuoritus.tehtävä  
AND Opiskelija.opiskelijanumero = Tehtäväsuoritus.opiskelija  
### tehtävä 14
Valitaan myös opiskelija
### Tehtävä 15
SELECT nimi FROM Kurssi k  
WHERE k.nimi
NOT IN (SELECT tehtävä FROM Kurssitehtävä)
### Tehtävä 16
SELECT kurssi AS kurssikoodi, COUNT(*) AS lukumäärä  
FROM kurssisuoritus   
GROUP BY kurssi
### Tehtävä 17
SELECT Kurssi.nimi AS kurssi , COUNT(*) AS lukumäärä  
FROM kurssisuoritus, Kurssi  
WHERE Kurssi.kurssitunnus = Kurssisuoritus.kurssi  
GROUP BY kurssi
### Tehtävä 18
SELECT Kurssi.nimi AS kurssi, COUNT(Kurssisuoritus.kurssi) AS lukumäärä  
FROM Kurssi LEFT JOIN Kurssisuoritus  
ON Kurssi.kurssitunnus = Kurssisuoritus.kurssi  
GROUP BY kurssi
### Tehtävä 19
CREATE TABLE Kurssi (kurssitunnus, nimi, kuvaus)
### Tehtävä 20
INSERT INTO Kurssi (kurssitunnus, nimi, kuvaus)  
VALUES ('12345', 'SQL-kielen perusteet', 'Hei maailma')  
SELECT Kurssi.nimi, Kurssi.kurssitunnus FROM Kurssi
### Tehtävä 21
CREATE TABLE Kurssi  
(
nimi varchar(50),  
kurssitunnus integer,  
kuvaus varchar(25)  
)  
PRAGMA TABLE_INFO(Kurssi)
### Tehtävä 22
CREATE TABLE Kurssi  
(  
kurssitunnus integer,  
nimi varchar(20),  
kuvaus varchar(20)  
)  
PRAGMA TABLE_INFO(Kurssi)
### Tehtävä 23
SELECT * FROM Opiskelija  
Lisäämällä toisen opiskelian, haku näyttää kahta opiskelijaa moneen kertaan.  
Virheviesti kertoo ettei kahta samnlaista opiskeliaa voi lisätä samalla tunnuksella.
### Tehtävä 24
CREATE TABLE Kurssi  
(  
kurssitunnus integer PRIMARY KEY,  
nimi varchar(25), 
kuvaus varchar(25)  
)  
### Tehtävä 25
PRAGMA foreign_keys = ON;  

CREATE TABLE Kurssitehtävä (  
tunnus integer PRIMARY KEY NOT NULL,  
tehtävä varchar(50) FOREIGN KEY NOT NULL,  
kurssi varchar(100) FOREIGN KEY NOT NULL  

CREATE TABLE Tehtävä  
tunnus integer PRIMARY KEY NOT NULL,  
nimi varchar(50) NOT NULL,  
kuvaus varchar(150)  
FOREIGN KEY(tehtävä) REFERENCES Tehtävä(tunnus)  
);
### Tehtävä 26
INSERT INTO Tehtävä(nimi) VALUES('tehtävä1');  
INSERT INTO Tehtävä(nimi) VALUES('tehtävä2');  
INSERT INTO Kurssitehtävä(tehtävä, kurssi) VALUES(1, 2);  
INSERT INTO Kurssitehtävä(tehtävä, kurssi) VALUES(2, 1);  

### Tehtävä 27
ALTER TABLELLA voi lisätä, poistaa tai muokata kolumneja jo olemassa olevassa tablessa.
