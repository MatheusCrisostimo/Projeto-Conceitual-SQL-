Cliente { idCliente integer pk null >* Veículo.idveículo Nome varchar Endereço varchar }

Ordem_de_Serviço { idOS integer pk null >* Peça.idPeça Numero integer Data_de_emissão date Valor_Total decimal status varchar data_de_conclusão date }

Veículo { idveículo varchar pk null >* Serviço.idServico Placa varchar unique Ano varchar }

Mecânico { idMecanico integer pk null >* Ordem_de_Serviço.idOS Nome varchar Endereço varchar Especialidade varchar }

Serviço { idServico integer pk null *> Ordem_de_Serviço.idOS Descrição varchar Valor varchar }

Peça { idPeça integer pk null Descrição varchar Valor decimal }