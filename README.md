Fila Digital para Atendimento

Bem-vindo ao repositório da Fila Digital para Atendimento! Este projeto foi criado como uma landing page responsiva para divulgar e coletar e-mails de pessoas interessadas no aplicativo.

🌐 Acesso Rápido

URL Hospedada no Firebase:https://tonavez-48061.web.app

🚀 Funcionalidades

Landing page moderna e responsiva (mobile e desktop);

Formulário de cadastro de e-mails com feedback interativo;

Integração com Google Apps Script para envio de e-mails e registro em planilha do Google Sheets;

Deploy com Firebase Hosting gratuito;

Imagem do app no centro da tela;

Suporte a atualização ignorando cache.

📊 Tecnologias Utilizadas

HTML5 e CSS3 (sem frameworks);

JavaScript Vanilla para interações;

Firebase Hosting;

Google Apps Script para backend do formulário;

Planilha Google (Sheets) para armazenamento.

📂 Estrutura de Diretórios

Landing page/
├── public/
│   ├── index.html
│   ├── style.css
│   ├── tela-inicial.jpg
├── .firebaserc
├── firebase.json

✍️ Configuração Manual

1. Firebase Hosting

firebase init hosting
firebase deploy --only hosting

2. Apps Script (Formulário)

Crie um novo script em Google Apps Script;

Use este modelo:

function doPost(e) {
  const ss = SpreadsheetApp.getActiveSpreadsheet().getActiveSheet();
  const dados = e.parameter;
  const nome = dados.nome || "Sem nome";
  const email = dados.email || "Sem email";
  const data = new Date();

  ss.appendRow([nome, email, data]);

  MailApp.sendEmail({
    to: "SEU_EMAIL@gmail.com",
    subject: "Novo interessado cadastrado",
    htmlBody: `📥 <b>Nome:</b> ${nome}<br><b>Email:</b> ${email}`
  });

  return ContentService.createTextOutput("Sucesso");
}

Publique como aplicativo da web (nova implantação);

Copie a URL do script e use no form action="URL" no HTML.

💌 Inserir Imagens no README

Para inserir imagens de exemplo da interface:

![Tela Desktop](caminho/da/imagem-desktop.png)
![Tela Mobile](caminho/da/imagem-mobile.png)

✨ Captura de Tela

Versão Desktop:
![image](https://github.com/user-attachments/assets/826f9898-bb4f-404f-b0a5-2b80e26d13f8)



Versão Mobile:
![image](https://github.com/user-attachments/assets/592c595a-aa00-4e58-b753-34b1de5ccbab)



🔧 Manutenção & Testes

Para evitar cache ao testar: Ctrl + F5 ou use o botão de recarregar forçado que foi incluído.

Para alterar os estilos, edite o arquivo style.css dentro da pasta public.

Sempre faça firebase deploy após atualizar arquivos.

📅 Autor

Fabiano Rodrigues LeiteProjeto criado com foco didático e funcional. Disponível para evolução com autenticação, banco de dados e push notifications.

🚫 Licença

Este projeto é livre para uso educacional e pessoal. Proibido uso comercial sem autorização.

Dúvidas? Sugestões? Me chame por aqui ou contribua com melhorias! 🚀

