# 🌱 Verdin · Controle Financeiro Pessoal

Um aplicativo de controle financeiro mensal simples, visual e direto ao ponto. Totalmente construído em HTML, CSS e JavaScript puro (sem necessidade de backend ou instalação), rodando 100% no navegador. 

A grande diferencial do Verdin é a sincronização na nuvem via GitHub API: você pode salvar e carregar seus dados financeiros direto em um repositório privado do GitHub, funcionando como um "banco de dados" gratuito e seguro.

Você também pode acessá-lo através do link https://luca-vieira.github.io/Verdin/

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
 
 
Aqui está um tutorial formatado em Markdown, perfeito para você copiar e colar diretamente no seu arquivo `README.md` do repositório. Ele explica de forma clara e visual como configurar a sincronização na nuvem usando o Fine-grained token.

***

## ☁️ Configurando a Sincronização na Nuvem (GitHub)

O Verdin permite que você salve e carregue seus dados financeiros direto em um repositório do GitHub, funcionando como um "banco de dados" gratuito e seguro. Isso permite que você acesse seus dados de qualquer dispositivo (celular, PC, tablet) sem precisar de um backend.

Para garantir a máxima segurança, utilizamos os **Fine-grained personal access tokens** do GitHub. Com eles, o acesso do aplicativo fica restrito **apenas ao repositório que você escolher**, sem expor o resto da sua conta.

Siga o passo a passo abaixo para configurar:

### 1. Crie um repositório para guardar seus dados
Se você ainda não tem um repositório para isso, crie um novo:
1. Vá em [New Repository](https://github.com/new) no GitHub.
2. Dê um nome (ex: `meu-backup-financeiro` ou use o próprio repositório do app).
3. **Importante:** Marque como **Private** (Privado) para que ninguém além de você tenha acesso aos seus dados.
4. Clique em *Create repository*.

### 2. Gere o Fine-grained Personal Access Token
Este token será a "chave" que o app usará para salvar o arquivo `.json` no seu repositório.

1. No GitHub, clique na sua foto de perfil (canto superior direito) > **Settings**.
2. No menu lateral esquerdo, role até o final e clique em **Developer settings**.
3. Vá em **Personal access tokens** > **Fine-grained tokens**.
4. Clique no botão **Generate new token**.
5. Preencha as informações:
   - **Token name:** Dê um nome (ex: `Token Verdin App`).
   - **Expiration:** Escolha por quanto tempo a chave vale (recomendado: 1 ano).
   - **Resource owner:** Selecione o seu próprio usuário.
   - **Repository access:** Selecione **Only select repositories** e, na lista suspensa, escolha o repositório que você criou no Passo 1.
6. Configure as Permissões:
   - Desça a página até a seção **Repository permissions**.
   - Procure pela opção **Contents**.
   - Mude a permissão de *No access* para **Read and write** (Ler e escrever).
7. Clique em **Generate token** no final da página.
8. **Copie o código gerado** (ele começa com `github_pat_...`). 
   > ⚠️ *Atenção: Você não poderá ver esse código novamente. Se perder, terá que gerar um novo.*

### 3. Configure no Aplicativo Verdin
Agora vamos conectar o app ao seu repositório.

1. Abra o Verdin no seu navegador.
2. Clique no botão **"Nuvem"** localizado na barra superior.
3. Preencha os campos do modal com as suas informações do GitHub:
   - **Usuário / Organização:** Seu nome de usuário (ex: `luca-vieira`).
   - **Repositório:** O nome do repo (ex: `Verdin` ou `meu-backup-financeiro`).
   - **Caminho do Arquivo:** O nome do arquivo que será salvo (ex: `dados.json` ou `backups/verdin.json`).
   - **Fine-grained Token:** Cole o token copiado no Passo 2.
4. Clique em **Salvar na Nuvem** para fazer o primeiro upload dos seus dados atuais.

Pronto! 🎉 Seu arquivo JSON foi commitado no seu repositório.

### 4. Como usar no dia a dia
- **No computador A:** Você adicionou novas despesas e quer ir para o celular. Abra o app, clique em **Nuvem** > **Salvar na Nuvem**.
- **No celular B:** Abra o app, clique em **Nuvem**. Preencha as mesmas configurações (se for a primeira vez no dispositivo) e clique em **Baixar**. Seus dados locais serão substituídos pelos dados da nuvem.

> 💡 **Dica:** O aplicativo salva suas configurações de nuvem no `localStorage` do navegador. Ou seja, você só precisa preencher esses dados de token uma vez por dispositivo/navegador.

O projeto é propositalmente contained em um único arquivo para facilitar o transporte e a hospedagem:

     index.html: Contém toda a estrutura HTML, estilos CSS (via tags <style>) e a lógica JavaScript (via tags <script>).

📝 Licença

Este projeto é de uso pessoal. Sinta-se livre para modificar e adaptar às suas necessidades.
⚠️ Aviso Legal

O Verdin é uma ferramenta de organização e visualização de dados. Ele não se conecta a bancos reais nem realiza transações financeiras. Os dados são de responsabilidade do usuário, armazenados localmente no navegador ou no próprio repositório GitHub do usuário.
