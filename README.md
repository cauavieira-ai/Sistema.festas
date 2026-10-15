##Sistema de Controle de Acesso - Gestão de Festas e Eventos##
Descrição do Minimundo
Organizar um evento envolve o controle rigoroso da lista de convidados para garantir a segurança, o conforto dos presentes e evitar a entrada de acompanhantes não autorizados ou penetras. O sistema automatiza a emissão de convites digitais com QR Code individual para cada convidado ou membro de um grupo/família e realiza a validação nominal na portaria do evento.

Contexto da Aplicação
O sistema será utilizado por três perfis de usuários:

Organizadores / Anfitriões: Administram o evento, definem a lista de convidados e gerenciam as autorizações de acesso.

Convidados: Confirmam presença (RSVP) para si e para seus dependentes/acompanhantes e recebem seus respectivos ingressos/convites digitais.

Portaria / Recepcionistas: Realizam o check-in dos participantes no dia do evento através da leitura do QR Code individual e conferência de documento.

Regras de Negócio
Os Organizadores/Anfitriões configuram o evento e gerenciam a lista global de convidados.

Cada convidado (seja titular ou acompanhante autorizado) possui o seu próprio Convite e QR Code individual e exclusivo.

A entrada no evento é liberada exclusivamente mediante a leitura do QR Code individual e validação do nome cadastrado no RSVP.

O registro de check-in é único por QR Code, invalidando o código imediatamente após o primeiro uso para impedir a entrada em duplicidade ou o reuso por terceiros.

Principais Processos
Cadastro do Evento: Registro das informações gerais do evento (tipo de festa, data, horário, local e capacidade máxima).

Gerenciamento de Convites: Emissão e envio de QR Codes individuais para cada pessoa cadastrada na lista final.

Confirmação de Presença (RSVP): Coleta, validação e atualização do nome completo de cada convidado ou acompanhante confirmados.

Controle de Portaria: Leitura do QR Code, validação nominal na lista em tempo real e registro com marca temporal (timestamp) da entrada.
