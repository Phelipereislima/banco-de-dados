CREATE TABLE Equipes (
    codigo int primary key AUTO_INCREMENT ,
    nome_tecnico varchar(150),
    nome_pais varchar(150),
    nome varchar(200)
);

CREATE TABLE Uniformes (
  codigo int PRIMARY KEY,
   cor_camisa varchar(15),
   cor_meiao varchar(15),
   cor_calcao varchar(15),
   numero int,
   codigo_equipe int   ,
   FOREIGN KEY (codigo_equipe) REFERENCES Equipes(codigo)
);
CREATE TABLE Jogadores (
    CPF varchar(20) PRIMARY KEY,
    Nome varchar(150),
    status int,
    codigo_equipe int,
    FOREIGN KEY (codigo_equipe) REFERENCES Equipes(codigo)
);

CREATE TABLE Estadio (
    codigo int PRIMARY KEY,
    nome varchar(200),
    cidade varchar(150),
    endereco varchar(254)
    );
CREATE TABLE Partidas (
    codigo int PRIMARY KEY,
    codigo_mandante int,
    codigo_visitante int,
    placar_mandante int,
    placar_visitante int,
    nome_juiz varchar(150),
    codigo_estadio int,
    FOREIGN KEY (codigo_mandante) REFERENCES Equipes(codigo),
    FOREIGN KEY (codigo_visitante ) REFERENCES Equipes(codigo),
    FOREIGN KEY (codigo_estadio) REFERENCES Estadio(codigo)
    );
