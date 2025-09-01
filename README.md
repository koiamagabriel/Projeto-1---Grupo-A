# Projeto-1---Grupo-A

UC_01 — Preparar Eleição nas Urnas
Função: Preparar e carregar nas urnas os dados da eleição
Atores: Administrador
Prioridade: Essencial
Pré-condição: Urnas cadastradas/validadas; base com candidatos e eleitores padronizados para todas as urnas do mesmo processo.
Pós-condição: Urnas autenticadas e carregadas, prontas para operar de forma autônoma.
Fluxo Principal
 • Administrador seleciona urnas-alvo.
 • Sistema valida urnas e compõe o pacote da eleição com cargos, candidatos padronizados e eleitores.
 • Sistema carrega/autentica o pacote nas urnas.
 • Sistema confirma conclusão.
Fluxo Secundário [FS001]
 • Inconsistência de dados → sistema bloqueia o carregamento e notifica.

UC_02 — Identificar Eleitor
Função: Confirmar o número de inscrição/documento do eleitor para iniciar a votação.
Atores: Eleitor
Prioridade: Essencial
Pré-condição: Urna carregada com listas de eleitores.
Pós-condição: Eleitor identificado e liberado para votar.
Fluxo Principal
 • Eleitor informa nº de inscrição/documento.
 • Sistema localiza o registro e exibe identificação.
 • Sistema valida elegibilidade do eleitor .
Fluxo Secundário [FS001]
 • Documento não encontrado → negar prosseguimento; orientar atendimento.
Fluxo Secundário [FS002]
 • Eleitor já votou → bloquear votação.

UC_03 — Registrar Voto
Função: Permitir ao eleitor registrar seu voto para cada cargo (até 8), com confirmação e opções de corrigir, branco e nulo.
Atores: Eleitor
Prioridade: Essencial
Pré-condição: UC_02 concluído; urna operando autonomamente após ter sido autenticada e carregada.
Pós-condição: Voto do eleitor gravado; eleitor marcado como “votou”
Fluxo Principal
 • Sistema apresenta a sequência de cargos .
 • Para cada cargo:
  – Eleitor digita o número do candidato.
  – Sistema mostra dados do candidato .
  – Eleitor confirma o voto.
 • Ao final da sequência, sistema registra conclusão do voto do eleitor.
Fluxo Secundário [FS001] — Corrigir Escolha
 • Antes de confirmar um cargo, eleitor solicita corrigir e digita novamente.
Fluxo Secundário [FS002] — Voto em Branco
 • Eleitor opta por branco para o cargo atual e confirma.
Fluxo Secundário [FS003] — Voto Nulo
 • Número digitado não corresponde a candidato válido; sistema indica nulo e permite confirmar.
Fluxo Secundário [FS004] — Elegibilidade negada
 • Caso o sistema detecte, antes da gravação final, que o eleitor já votou , cancela o registro e orienta atendimento.

UC_04 — Encerrar Votação e Enviar Apuração
Função: Encerrar a votação na urna e transmitir a apuração à central quando a comunicação for solicitada.
Atores: Administrador
Prioridade: Importante
Pré-condição: Período de votação finalizado; apuração local consolidada.
Pós-condição: Apuração enviada contendo total por cargo e contagens de brancos, nulos e ausentes.
Fluxo Principal
 • Operador encerra a votação.
 • Sistema consolida votos por cargo e contabiliza brancos, nulos e ausentes.
 • Sistema solicita comunicação e envia a apuração à central.
 • Sistema registra confirmação de envio/recebimento.
Fluxo Secundário [FS001]
 • Falha de comunicação → armazenar e re-tentar até sucesso (política de reenvio).

UC_05 — Totalizar e Divulgar Resultados
Função: Totalizar resultados por urna e no geral, gerando tabelas/gráficos.
Atores: Administrador
Prioridade: Importante
Pré-condição: Apurações recebidas das urnas.
Pós-condição: Relatórios por urna e totalizados; com brancos, nulos e ausentes.
Fluxo Principal
 • Administrador escolhe o escopo.
 • Sistema totaliza e produz tabelas ou gráficos.
 • Sistema disponibiliza/expõe os relatórios.
Fluxo Secundário [FS001]
 • Apuração incompleta → emitir parcial com aviso.



 


