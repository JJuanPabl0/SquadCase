# 📡 Padrão Pub/Sub (Publish/Subscribe)

O padrão Pub/Sub permite que partes do sistema publiquem mensagens enquanto outras partes assinam (subscribe) para recebê-las — sem dependerem umas das outras.
Isso deixa o sistema desacoplado, escalável e assíncrono.

# 🔍 Diferença entre Observer e Pub/Sub

### 🟦 Observer (Design Pattern)

- Muito parecido com Pub/Sub, por isso são frequentemente confundidos.

- O sujeito conhece diretamente seus observadores.

- A comunicação é imediata, com acoplamento direto.

### 🟩 Pub/Sub

- A comunicação acontece por meio de um intermediário (broker).

- Publicadores e assinantes não se conhecem.

- Ideal para sistemas assíncronos, distribuídos e que não podem travar.

**Muito utilizado em:**

Sistemas de mensageria, monitoramento, logs IoT, jogos online, aplicações financeiras etc...

## 🧠 A Ideia do Pub/Sub

O padrão Pub/Sub funciona assim:

- Publisher → quem publica as mensagens

- Topic → o canal/categoria da mensagem (ex: esportes, política, games)

- Subscriber → quem assina um ou mais tópicos para receber mensagens

Quando uma nova mensagem é publicada em um tópico, todos os assinantes daquele tópico recebem a atualização.