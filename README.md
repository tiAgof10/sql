-- Criação da Tabela Produtos
CREATE TABLE Produtos (
    id_produto INTEGER PRIMARY KEY AUTOINCREMENT,
    nome VARCHAR(255) NOT NULL,
    descricao TEXT,
    preco DECIMAL(10,2) NOT NULL,
    estoque INTEGER NOT NULL
);

-- Inserção de Registros na Tabela Produtos
INSERT INTO Produtos (nome, descricao, preco, estoque) VALUES
('Café Expresso', 'Café 100% Arábica, curto e encorpado', 7.50, 100),
('Livro "A Revolução dos Bichos"', 'Clássico de George Orwell', 35.00, 50),
('Bolo de Cenoura', 'Fatia de bolo de cenoura com cobertura de chocolate', 12.00, 30);

-- Criação da Tabela Pedidos
CREATE TABLE Pedidos (
    id_pedido INTEGER PRIMARY KEY AUTOINCREMENT,
    id_produto INTEGER NOT NULL,
    quantidade INTEGER NOT NULL,
    data_pedido DATE NOT NULL,
    valor_total DECIMAL(10,2) NOT NULL,
    FOREIGN KEY (id_produto) REFERENCES Produtos(id_produto)
);

-- Inserção de Registros na Tabela Pedidos
INSERT INTO Pedidos (id_produto, quantidade, data_pedido, valor_total) VALUES
(1, 2, '2025-07-04', 15.00), -- 2 Cafés Expressos
(2, 1, '2025-07-04', 35.00), -- 1 Livro "A Revolução dos Bichos"
(3, 3, '2025-07-03', 36.00); -- 3 Bolos de Cenoura
git commit -m "feat: Adiciona modelo inicial de banco de dados para produtos e pedidos"
