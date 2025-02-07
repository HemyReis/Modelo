CREATE TABLE Faculdade (
    id_faculdade INT PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(100) NOT NULL,
    endereco VARCHAR(255) NOT NULL
);

CREATE TABLE Turma (
    id_turma INT PRIMARY KEY AUTO_INCREMENT,
    nome_turma VARCHAR(100) NOT NULL,
    id_faculdade INT NOT NULL,
    FOREIGN KEY (id_faculdade) REFERENCES Faculdade(id_faculdade) ON DELETE CASCADE
);

CREATE TABLE Aluno (
    id_aluno INT PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(100) NOT NULL,
    cpf VARCHAR(14) UNIQUE NOT NULL,
    data_nascimento DATE NOT NULL,
    endereco VARCHAR(255) NOT NULL
);

CREATE TABLE Matricula (
    id_matricula INT PRIMARY KEY AUTO_INCREMENT,
    id_aluno INT NOT NULL,
    id_turma INT NOT NULL,
    data_matricula DATE NOT NULL,
    FOREIGN KEY (id_aluno) REFERENCES Aluno(id_aluno) ON DELETE CASCADE,
    FOREIGN KEY (id_turma) REFERENCES Turma(id_turma) ON DELETE CASCADE
);
