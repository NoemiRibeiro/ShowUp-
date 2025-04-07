# ShowUp-
Projeto de app para a disciplina de Laboratório de Engenharia de Software - Curso de Análise e Desenvolvimento de Sistemas da Fatec Baixada Santista - Rubens Lara

-- Passo 1: Criar o banco de dados
CREATE DATABASE show_up;

-- Passo 2: Conectar ao banco de dados
\c show_up

-- Passo 3: Criar a tabela
CREATE TABLE usuario (
    idUsuario SERIAL PRIMARY KEY,
    usuario VARCHAR(100) NOT NULL,
    emailUsuario VARCHAR(100) UNIQUE NOT NULL,
    senha VARCHAR(15) NOT NULL,
    dtNascimento DATE NOT NULL,
    bio TEXT,
    dtCadastro TIMESTAMP NOT NULL,
    ativo BOOLEAN
    
);

CREATE TABLE evento (
    idEvento SERIAL PRIMARY KEY,
    idUsuario INTEGER NOT NULL,
    evento VARCHAR(100) NOT NULL,
    diaUnico BOOLEAN,
    dtInicio DATE NOT NULL,
    hrInicio TIME NOT NULL,
    dtFim DATE NOT NULL,
    hrFim TIME,
    descricao TEXT NOT NULL,
    idLocalizacao INTEGER NOT NULL, 
    dtCadastro TIMESTAMP NOT NULL,
    publico BOOLEAN
    
);

CREATE TABLE status_evento (
    idStatus SERIAL PRIMARY KEY,
    status VARCHAR(50) NOT NULL.
    statusAtivo BOOLEAN
);

CREATE TABLE tipo_evento (
    idTipo SERIAL PRIMARY KEY,
    tipo VARCHAR(50) NOT NULL.
    tipoAtivo BOOLEAN
);

CREATE TABLE conexao (
    idStatus SERIAL PRIMARY KEY,
    idUsuario INTEGER NOT NULL,
    idUsuario INTEGER NOT NULL,
    aceiteConexao BOOLEAN
);
CREATE TABLE convite (
    idStatus SERIAL PRIMARY KEY,
    idEvento INTEGER NOT NULL,
    idUsuario INTEGER NOT NULL,
    aceiteConvite BOOLEAN
);

CREATE TABLE localizacao(
    idLocalizacao SERIAL PRIMARY KEY,
    dsLocalizacao VARCHAR(100) NOT NULL,
    cep INTEGER,
    dsLogradouro VARCHAR(150) NOT NULL,
    numero VARCHAR(007) NOT NULL,
    bairro VARCHAR(020) NOT NULL,
    complemento VARCHAR(020),
    cidade VARCHAR(100) NOT NULL,
    estado VARCHAR(002) NOT NULL,
    pais VARCHAR(050) NOT NULL
);

-- Passo 4: Fechar a conexão
\q
