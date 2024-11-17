# Tecnoligias utilizadas
Ubuntu ou Intancia na provide Azure / AWS obs: Utilize uma T2 larger para usar Jenkins e Sonarqube
- Docker
- Jenkins
- Sonarqube
- Dempendency Checks
--------------

## Análise Detalhada das Etapas do Pipeline
# Compreendendo o Fluxo de Trabalho

O pipeline apresentado automatiza o processo de desenvolvimento, teste, construção e implantação de uma aplicação Java. Ele integra diversas ferramentas e tecnologias para garantir a qualidade e a eficiência do processo de entrega.

# Descrição Detalhada de Cada Etapa

- stage('Git Checkout ') Checkout do Git:

Objetivo: Baixar o código fonte do repositório Git para a máquina onde o pipeline está sendo executado.
Detalhes: Especifica o branch main e a URL do repositório.

- stage('Code Compile') Compilação do Código:

Objetivo: Compilar o código fonte Java em bytecode.
Detalhes: Utiliza o Maven para executar o comando compile.

- stage('Sonarqube Analysis') Análise SonarQube:

Objetivo: Analisar o código em busca de problemas de qualidade, segurança e cobertura de testes.
Detalhes: Utiliza o SonarQube Scanner para analisar o código e gerar um relatório detalhado.

- stage('OWASP Dependency Check') Verificação de Dependências OWASP:

Objetivo: Verificar se as dependências do projeto possuem vulnerabilidades conhecidas.
Detalhes: Utiliza a ferramenta OWASP Dependency Check para analisar as dependências e gerar um relatório.

- stage('Build') Construção do Projeto:

Objetivo: Construir o projeto em um artefato final, como um JAR ou WAR.
Detalhes: Utiliza o Maven para executar o comando clean package.

- stage('Docker Build & Push') Construção e Envio da Imagem Docker:

Objetivo: Criar uma imagem Docker com a aplicação e enviá-la para um registro Docker.
Detalhes: Utiliza o Docker para construir a imagem, taguea-la e enviá-la para o registro.

- stage('Docker Deploy') Implantação da Imagem Docker:

Objetivo: Executar um container Docker com a imagem recém-construída.
Detalhes: Utiliza o Docker para executar um container e mapear a porta 8081 da máquina host para a porta 8081 do container.
