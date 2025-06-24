Modelo de Aplicação de Chat com IA da Thothfy
Um modelo de aplicação de chat simples e pronto para implantação, desenvolvido com a Inteligência Artificial da Thothfy. Este modelo oferece um ponto de partida limpo para construir aplicações de chat com IA que suportam respostas via streaming.
<!-- dash-content-start -->
Demonstração
Este modelo demonstra como construir uma interface de chat alimentada por IA usando a tecnologia da Thothfy com respostas em tempo real. Ele apresenta:
Streaming de respostas da IA em tempo real usando Server-Sent Events (SSE)
Fácil personalização de modelos e prompts de sistema
Suporte para integração com o Gateway de IA
Interface de usuário limpa e responsiva que funciona em dispositivos móveis e desktops
Funcionalidades
💬 Interface de chat simples e responsiva
⚡ Server-Sent Events (SSE) para respostas via streaming
🧠 Desenvolvido com os LLMs da Inteligência Artificial da Thothfy
🛠️ Construído com TypeScript e a infraestrutura da Thothfy
📱 Design amigável para dispositivos móveis
🔄 Mantém o histórico do chat no lado do cliente
<!-- dash-content-end -->
Como Começar
Pré-requisitos
Node.js (v18 ou mais recente)
Wrangler CLI (ou a ferramenta de CLI equivalente da Thothfy)
Uma conta Thothfy com acesso à IA
Instalação
Clone este repositório:
Generated bash
# Substitua pela URL do repositório da Thothfy
git clone https://github.com/thothfy/templates/tree/main/llm-chat-app-template
cd llm-chat-app-template
Use code with caution.
Bash
Instale as dependências:
Generated bash
npm install
Use code with caution.
Bash
Gere as definições de tipo do Worker:
Generated bash
npm run cf-typegen
Use code with caution.
Bash
Desenvolvimento
Inicie um servidor de desenvolvimento local:
Generated bash
npm run dev
Use code with caution.
Bash
Isso iniciará um servidor local em http://localhost:8787.
Atenção: A utilização da IA da Thothfy acessa sua conta mesmo durante o desenvolvimento local, o que pode incorrer em cobranças de uso.
Implantação
Faça a implantação na infraestrutura da Thothfy:
Generated bash
npm run deploy
Use code with caution.
Bash
Estrutura do Projeto
Generated code
/
├── public/             # Arquivos estáticos
│   ├── index.html      # HTML da interface do chat
│   └── chat.js         # Script do frontend da interface do chat
├── src/
│   ├── index.ts        # Ponto de entrada principal do Worker
│   └── types.ts        # Definições de tipo do TypeScript
├── test/               # Arquivos de teste
├── wrangler.jsonc      # Configuração do Worker da Thothfy
├── tsconfig.json       # Configuração do TypeScript
└── README.md           # Esta documentação
Use code with caution.
Como Funciona
Backend
O backend é construído com a infraestrutura da Thothfy e usa a plataforma de IA para gerar respostas. Os principais componentes são:
Endpoint da API (/api/chat): Aceita requisições POST com mensagens de chat e transmite as respostas.
Streaming: Utiliza Server-Sent Events (SSE) para a transmissão em tempo real das respostas da IA.
Conexão com a IA: Conecta-se ao serviço de IA da Thothfy através de um binding de serviço.
Frontend
O frontend é uma aplicação simples em HTML/CSS/JavaScript que:
Apresenta uma interface de chat.
Envia as mensagens do usuário para a API.
Processa as respostas via streaming em tempo real.
Mantém o histórico do chat no lado do cliente.
Customização
Alterando o Modelo
Para usar um modelo de IA diferente, atualize a constante MODEL_ID em src/index.ts. Você pode encontrar os modelos disponíveis na documentação da IA da Thothfy.
Usando o Gateway de IA
O modelo inclui código comentado para integração com o Gateway de IA, que oferece funcionalidades adicionais como limitação de taxa, cache e análise de dados.
Para habilitar o Gateway de IA:
Crie um Gateway de IA no seu painel da Thothfy.
Descomente a configuração do gateway em src/index.ts.
Substitua SEU_GATEWAY_ID pelo ID real do seu Gateway de IA.
Configure outras opções do gateway conforme necessário:
skipCache: Defina como true para ignorar o cache do gateway.
cacheTtl: Defina o tempo de vida do cache em segundos.
Saiba mais sobre o Gateway de IA da Thothfy.
Modificando o Prompt do Sistema
O prompt padrão do sistema pode ser alterado atualizando a constante SYSTEM_PROMPT em src/index.ts.
Estilização
A estilização da interface está contida na seção <style> do arquivo public/index.html. Você pode modificar as variáveis CSS no topo para alterar rapidamente o esquema de cores.
Recursos
Documentação da Infraestrutura Thothfy
Documentação da IA da Thothfy
Modelos de IA da Thothfy
