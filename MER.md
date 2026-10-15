# Modelo de Entidade e Relacionamento (MER) - Gestão de Festas e Eventos

## 1. Entidades

- **Organizador:** Representa a pessoa ou empresa responsável por criar, gerenciar e financiar o evento.
- **Evento:** Representa a festa ou evento específico cadastrado no sistema.
- **Convidado:** Representa cada pessoa individual (titular ou acompanhante) cadastrada para comparecer ao evento.
- **Convite:** Representa o passe/credencial digital (QR Code) individual e exclusivo gerado para cada convidado.
- **Portaria:** Representa o registro físico de check-in (validação do QR Code) realizado na entrada do evento.

---

## 2. Relacionamentos e Cardinalidades

- **[Organizador] (1,1) ------ (1,n) [Evento]**
  Um Organizador pode criar/gerenciar um ou vários Eventos, mas cada Evento pertence obrigatoriamente a exatamente 1 Organizador.

- **[Evento] (1,1) ------ (1,n) [Convidado]**
  Um Evento possui uma lista com um ou vários Convidados cadastrados. Cada Convidado está associado a exatamente 1 Evento.

- **[Evento] (1,1) ------ (1,n) [Convite]**
  Um Evento gera múltiplos Convites individuais para distribuição aos convidados. Cada Convite pertence a exatamente 1 Evento.

- **[Convidado] (1,1) ------ (1,1) [Convite]**
  Cada Convidado possui exatamente 1 Convite/QR Code exclusivo, e cada Convite pertence a apenas 1 Convidado.

- **[Convite] (1,1) ------ (0,1) [Portaria]**
  Cada Convite pode ter no máximo 1 registro de entrada na Portaria (0 quando ainda não entrou, 1 quando realizou o check-in), invalidando o código após o primeiro uso.

---

## 3. Atributos

### Organizador
- `id_organizador` (PK)
- `nome`
- `telefone`
- `email`

### Evento
- `id_evento` (PK)
- `id_organizador` (FK)
- `nome_evento`
- `tipo_evento` (Ex: Aniversário, Casamento, Corporativo)
- `data_hora`
- `local`
- `capacidade_maxima`

### Convidado
- `id_convidado` (PK)
- `id_evento` (FK)
- `nome_completo`
- `grupo_familiar` / `grupo_acompanhante`
- `eh_titular` (Booleano: Sim/Não)
- `status_rsvp` (Pendente, Confirmado, Recusado)

### Convite
- `id_convite` (PK)
- `id_convidado` (FK - Vincula diretamente ao convidado)
- `id_evento` (FK)
- `codigo_qr` (Único para cada convidado)
- `status_convite` (Ativo, Utilizado, Cancelado)

### Portaria
- `id_entrada` (PK)
- `id_convite` (FK - Vincula diretamente ao convite validado)
- `data_hora_entrada`
- `operador_portaria`


## 4. Diagrama Entidade e Relacionamento (DER)

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/6283b2b2-ce96-4da1-b60d-9db6a25235dd" />



