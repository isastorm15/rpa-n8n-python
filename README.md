# Assistente Inteligente de E-mails com n8n + Python

Projeto desenvolvido como desafio prático de RPA utilizando n8n, Python, API de IA e Gmail.

## Objetivo

Automatizar o recebimento e tratamento de solicitações enviadas por um webhook.

O fluxo:

1. Recebe nome, e-mail, assunto e mensagem.
2. Classifica a solicitação.
3. Envia os dados para uma IA gerar uma resposta profissional.
4. Envia a resposta por e-mail.
5. Retorna uma confirmação ao sistema que chamou o webhook.

## Tecnologias

- n8n
- Python
- API de IA
- Gmail
- Webhooks
- JSON

## Estrutura

```text
rpa-n8n-python/
├── README.md
├── .gitignore
├── descricao-entrega.txt
├── exemplos/
│   └── entrada.json
├── python/
│   └── classificador.py
└── workflow/
    └── automacao-email-n8n.json
```

## Exemplo de entrada

```json
{
  "nome": "João Silva",
  "email": "joao@email.com",
  "assunto": "Solicitação de suporte",
  "mensagem": "Estou com dificuldade para acessar minha conta."
}
```

## Como usar no n8n

1. Abra o n8n.
2. Crie um workflow novo.
3. Use a opção **Import from File**.
4. Importe `workflow/automacao-email-n8n.json`.
5. Abra o node **Gerar resposta com IA**.
6. Troque `COLOQUE_SUA_CHAVE_AQUI` pela sua chave da API de IA, ou configure uma credencial segura no n8n.
7. Abra o node **Enviar e-mail**.
8. Configure sua credencial do Gmail.
9. Salve e ative o workflow.
10. Copie a URL de produção do Webhook e faça um teste.

> Importante: nunca publique chaves reais no GitHub.

## Classificação em Python

O arquivo `python/classificador.py` contém a mesma ideia de classificação usada no fluxo e pode ser executado separadamente para demonstrar o uso de Python no projeto.

## Segurança

- Não publique tokens ou senhas.
- Prefira credenciais armazenadas no próprio n8n.
- Use HTTPS no webhook.
- Em produção, adicione autenticação ao webhook.
- Não armazene dados pessoais além do necessário.

## Resultado esperado

Ao receber uma solicitação, o fluxo classifica o assunto, gera uma resposta adequada com IA e envia um e-mail ao solicitante de forma automática.
