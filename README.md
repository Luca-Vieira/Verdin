🌱 Verdin · Controle Financeiro Pessoal

Um aplicativo de controle financeiro mensal simples, visual e direto ao ponto. Totalmente construído em HTML, CSS e JavaScript puro (sem necessidade de backend ou instalação), rodando 100% no navegador. 

A grande diferencial do Verdin é a sincronização na nuvem via GitHub API: você pode salvar e carregar seus dados financeiros direto em um repositório privado do GitHub, funcionando como um "banco de dados" gratuito e seguro.

Verdin Screenshot 
✨ Funcionalidades

    📊 Dashboard Interativo: Visão geral de receitas, despesas, saldo do mês e total guardado, com gráficos dinâmicos (Receitas x Despesas e Categorias).
    💵 Gestão de Lançamentos: Cadastro de receitas e despesas avulsas, com filtros por mês, categoria, status (pago/pendente/vencido) e busca textual.
    🔁 Contas Fixas e Parceladas: 
        Cadastro de contas mensais recorrentes (ex: Aluguel, Internet).
        Suporte a despesas parceladas (ex: TV 10x de R$ 200). O sistema controla em qual parcela você está e gera o lançamento do mês com 1 clique.
    🎯 Metas e Reservas: Crie metas (ex: Reserva de Emergência, Viagem) e registre aportes. Acompanhe a evolução do seu patrimônio com gráfico de linha.
    🔗 Associações: Relacione uma despesa a uma receita (ex: "Salário paga Aluguel") para entender o fluxo do seu dinheiro.
    📅 Linha do Tempo: Visualização cronológica de todas as movimentações de um mês específico.
    ☁️ Sincronização via GitHub: Salve e carregue seu arquivo JSON direto de um repositório do GitHub.
    📦 Exportar/Importar JSON: Faça backups locais manuais ou mova dados entre dispositivos facilmente.
    💾 Offline-first: Os dados são salvos no localStorage do navegador, funcionando perfeitamente sem internet (apenas a sincronização na nuvem exige internet).

🛠️ Tecnologias Utilizadas

    HTML5 & CSS3: Estrutura e estilização (Design escuro, responsivo para mobile e desktop).
    JavaScript (Vanilla): Toda a lógica de estado, cálculos, filtros e manipulação de DOM.
    Chart.js: Biblioteca para renderização dos gráficos.
    GitHub REST API: Utilizada para fazer commit e ler o arquivo JSON de configuração direto do repositório.

🚀 Como usar (Localmente)

Como é um arquivo único, você pode simplesmente baixar o index.html e abri-lo no seu navegador.

    Clone o repositório:

    git clone https://github.com/SEU_USUARIO/SEU_REPOSITORIO.git

    Entre na pasta:
    bash
     
      
     
     
    cd SEU_REPOSITORIO
     
     
    Abra o arquivo index.html no seu navegador (Google Chrome, Firefox, Edge, etc).
    Pronto! O app já está funcionando e salvando dados localmente.

(Opcional): Se quiser rodar com um servidor local (para evitar bloqueios de CORS em alguns navegadores):
bash
 
  
 
 
# Usando Python
python -m http.server 8000
# Acesse http://localhost:8000
 
 
☁️ Configurando a Sincronização com GitHub

Para que seus dados fiquem salvos na nuvem e você possa acessá-los de qualquer dispositivo, o Verdin usa a API do GitHub para salvar um arquivo .json no seu repositório.

Siga os passos abaixo para configurar:
1. Crie um repositório no GitHub

     Vá em New Repository.
     Dê um nome (ex: meu-backup-financeiro).
     Importante: Marque como Private (Privado) para que ninguém além de você tenha acesso aos seus dados.
     Clique em Create repository.

2. Gere um Personal Access Token (PAT)

     No GitHub, clique na sua foto de perfil (canto superior direito) > Settings.
     Role até o final no menu lateral esquerdo e clique em Developer settings.
     Vá em Personal access tokens > Tokens (classic).
     Clique em Generate new token (classic).
     Dê um nome (ex: Token Verdin App).
     Em Select scopes, marque apenas a opção repo (isso concede permissão de leitura/escrita em repositórios).
     Clique em Generate token e copie o código gerado (começa com ghp_...). Ele não será mostrado novamente.

3. Configure no App Verdin

     Abra o Verdin e clique no botão "Nuvem" na barra superior.
     Preencha os campos:
         Usuário: Seu nome de usuário do GitHub (ex: joaosilva).
         Repositório: O nome do repositório que você criou (ex: meu-backup-financeiro).
         Caminho do Arquivo: O nome do arquivo que será salvo (ex: dados.json ou backups/verdin.json).
         Token: Cole o token gerado no passo anterior.
     Clique em Salvar na Nuvem para fazer o primeiro upload dos seus dados atuais.

Pronto! Agora, sempre que fizer alterações em um dispositivo, clique em "Salvar na Nuvem". Ao abrir o app no celular ou em outro PC, clique em "Baixar" para sincronizar.

(Nota: O token e as configurações ficam salvos apenas no localStorage do navegador onde você configurou. Você precisará repetir o passo 3 em cada navegador/dispositivo que for usar).
📂 Estrutura do Projeto

O projeto é propositalmente contained em um único arquivo para facilitar o transporte e a hospedagem:

     index.html: Contém toda a estrutura HTML, estilos CSS (via tags <style>) e a lógica JavaScript (via tags <script>).

📝 Licença

Este projeto é de uso pessoal. Sinta-se livre para modificar e adaptar às suas necessidades.
⚠️ Aviso Legal

O Verdin é uma ferramenta de organização e visualização de dados. Ele não se conecta a bancos reais nem realiza transações financeiras. Os dados são de responsabilidade do usuário, armazenados localmente no navegador ou no próprio repositório GitHub do usuário.
