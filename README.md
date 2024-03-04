# Projeto-Conceitual-de-Banco-de-Dados-E-COMMERCE-Final-
Projeto de E-commerce - Referente a venda de produto

https://dbdesigner.page.link/ikUap8tNtvEmEe6e8


Cliente {
	idCliente varchar pk null >* Pedido.idPedido
	Nome integer
	Pagamento integer >* Pagamento.Forma_de_Pagamento
	CPF_ou_CNPJ varchar null unique
}

Pedido {
	idPedido integer pk null *>* Produto.idProduto
	Status_do_Pedido varchar
	descrição varchar
	Frete float
}

Fornecedor {
	Razão_Social varchar
	CNPJ varchar unique
	idFornecedor integer pk null
}

Estoque {
	idEstoque integer pk null *>* Produto.idProduto
	Local varchar
}

Produto {
	idProduto integer pk null *>* Fornecedor.idFornecedor
	Categoria varchar
	Descrição varchar
	Valor varchar
}

Terceiro_Vendedor {
	idVendedor integer pk null unique *>* Produto.idProduto
	Razão_Socual varchar
	Local varchar
}

Entrega {
	idEntrega integer pk null *> Pedido.idPedido
	Status integer
	Código_de_rastreio integer
}

Pagamento {
	idPagamento integer pk null
	Forma_de_Pagamento varchar null
}

