# 12 fatores

## Características

- Melhores práticas para o desenvolvimento de aplicativos em nuvem.
- Especificamente para o modelo de Software como Serviço ([SaaS](<../../Linguagens e padrões/Plataformas de desenvolvimento.md#saas-software-como-serviço>)).
- Diretrizes para criar aplicativos escaláveis, flexíveis e fáceis de manter.
- Apresentados por Adam Wiggins, um dos fundadores do Heroku.

## Fatores de sucesso de uma aplicação

1. **Código Base:** Utilize um único repositório de código base, rastreando o código-fonte de todas as dependências com ferramentas de controle de versão.

2. **Dependências:** Explicite e isole as dependências. Não confie no ambiente para fornecer dependências, pois isso pode levar a problemas de compatibilidade.

3. **Configurações:** Armazene configurações no ambiente. Evite a configuração embutida no código, permitindo que as configurações sejam facilmente ajustadas sem modificar o código.

4. **Backing Services (Serviços de Apoio):** Trate os serviços de apoio (como bancos de dados, filas de mensagens) como recursos anexados que podem ser facilmente substituídos. Não dependa de configurações específicas do ambiente.

5. **Build, Release, Run (Compilação, Lançamento, Execução):** Separe essas três etapas para garantir que o código seja construído, lançado e executado de maneira consistente em diferentes ambientes.

6. **Processos:** Execute a aplicação como um ou mais processos sem estado. Isso facilita a escalabilidade, a recuperação de falhas e a gestão de recursos.

7. **Vínculo de Porta (Port Binding):** Exponha serviços através de uma porta. Como um endereço web onde uma API pode ser consumida. As aplicações devem ser autossuficientes e não depender do servidor web para exportar serviços.

8. **Concorrência:** Dimensione por meio do modelo de processo. Execute várias instâncias da aplicação para atender à demanda, equilibrando a carga entre elas.

9. **Descartabilidade (Disposability):** Projete para fácil escalabilidade horizontal, permitindo que as instâncias da aplicação sejam adicionadas ou removidas conforme necessário.

10. **Dev/prod parity (Paridade entre Desenvolvimento e Produção):** Mantenha ambientes de desenvolvimento, teste e produção o mais semelhantes possível para evitar surpresas inesperadas em produção.

11. **Logs:** Trate os logs como fluxo de eventos. Os logs devem ser tratados como streams de eventos, facilitando a análise e a resolução de problemas.

12. **Administração de Processos (Admin Process):** Execute tarefas de administração como processos únicos e independentes. Isso facilita a automação e evita dependências complexas entre tarefas.

Esses fatores fornecem uma estrutura sólida para o desenvolvimento de aplicativos SaaS modernos, promovendo práticas como escalabilidade, manutenção facilitada e resiliência.
