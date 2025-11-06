```mermaid
  stateDiagram-v2
  direction LR

  [*] --> FazerLogin
  [*] --> CriarConta

  CriarConta --> Usuario
  CriarConta --> Motorista

  FazerLogin --> Conta
  Conta --> Usuario
  Conta --> Motorista

  Motorista --> IniciarServico
  Usuario --> SolicitarServico

  SolicitarServico --> Pagamento
  Pagamento --> Credito
  Pagamento --> Debito
  Pagamento --> Dinheiro
  Pagamento --> Pix

  Pix --> Negado
  Debito --> Negado
  Credito --> Negado
  Dinheiro --> Negado

  Pix --> Aprovado
  Dinheiro --> Aprovado
  Credito --> Aprovado
  Debito --> Aprovado

  Negado --> SolicitarServico

  Aprovado --> EsperandoMotorista
  EsperandoMotorista --> ClienteEmEspera
  IniciarServico --> ClienteEmEspera

  ClienteEmEspera --> CorridaEmAndamento
  CorridaEmAndamento --> FinalizarCorrida
  FinalizarCorrida --> Usuario
  Usuario --> AvaliacaoDaCorrida



