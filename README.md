
--Código para a criação das tabelas do banco de dados.

-- Tabela para quartos
CREATE TABLE room (
  id SERIAL PRIMARY KEY,
  capacity SMALLINT,
  description VARCHAR(500),
  name VARCHAR(100),
  price_hour NUMERIC(10, 2) -- Melhorei a precisão do tipo de dado para NUMERIC(10, 2)
);

-- Tabela para usuários
CREATE TABLE users (
  id SERIAL PRIMARY KEY,
  username VARCHAR(100),
  email VARCHAR(100),
  password VARCHAR(100),
  address VARCHAR(200),
  city VARCHAR(100),
  state CHAR(2)
);

-- Tabela para reservas
CREATE TABLE reservation (
  id SERIAL PRIMARY KEY,
  event_category VARCHAR(100),
  date DATE,
  start_time TIME,
  end_time TIME,
  room_id INTEGER,
  user_id INTEGER,
  access_key VARCHAR(100),
  status VARCHAR(50),
  FOREIGN KEY (room_id) REFERENCES room (id),
  FOREIGN KEY (user_id) REFERENCES users (id)
);

-- Tabela para empresas
CREATE TABLE company (
  id SERIAL PRIMARY KEY,
  business_name VARCHAR(200),
  cnpj CHAR(14),
  postal_code CHAR(8),
  email VARCHAR(100),
  address VARCHAR(200),
  city VARCHAR(100),
  neighborhood VARCHAR(100),
  telephone CHAR(20)
);
