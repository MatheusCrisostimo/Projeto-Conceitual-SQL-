# Projeto-Conceitual-Oficina

https://dbdesigner.page.link/DAufXQtdtS51G6PX6

Cliente { idCliente integer pk null >* Veículo.idveículo Nome varchar Endereço varchar }

Ordem_de_Serviço { idOS integer pk null >* Peça.idPeça Numero integer Data_de_emissão date Valor_Total decimal status varchar data_de_conclusão date }

Veículo { idveículo varchar pk null >* Serviço.idServico Placa varchar unique Ano varchar }

Mecânico { idMecanico integer pk null >* Ordem_de_Serviço.idOS Nome varchar Endereço varchar Especialidade varchar }

Serviço { idServico integer pk null *> Ordem_de_Serviço.idOS Descrição varchar Valor varchar }

Peça { idPeça integer pk null Descrição varchar Valor decimal }


# Projeto-Conceitual-Oficina v2
Cliente {
	idCliente int pk null >* Pedido.idPedido
	Nome_completo varchar unique
	Contato char
	Perfil varchar
}

Ordem_de_Serviço {
	idOrdem_de_Serviço int pk null
	Descrição varchar
	Prioridade varchar
}

Responsável {
	idResponsável int pk null > Ordem_de_Serviço.idOrdem_de_Serviço
	Setor varchar
	Matricula varchar unique
	Cargo varchar
}

Pedido {
	idPedido int pk null increments *>* Responsável.idResponsável
	Descrição varchar
	Titulo_do_pedido varchar
	Tipo_de_problema enum
	Prioridade enum def(Baixa)
}

