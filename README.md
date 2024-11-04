# Password Manager - Gerenciador de Senhas com Criptografia Fernet

## Descrição do Projeto

Este projeto é um gerenciador de senhas seguro em Python que utiliza a criptografia Fernet para armazenar senhas de forma protegida. Ele permite que você salve e recupere senhas associadas a domínios específicos, com uma camada adicional de segurança através da geração e arquivamento de uma chave de criptografia.

## Funcionalidades

- **Criação e Armazenamento de Chave**: Gera uma chave de criptografia aleatória para proteger suas senhas.
- **Armazenamento Seguro de Senhas**: As senhas são criptografadas com a chave gerada e armazenadas em um banco de dados de texto simples.
- **Recuperação de Senhas**: Você pode recuperar as senhas armazenadas para um domínio específico, desde que forneça a chave correta.
- **Arquivamento Automático de Chave**: O projeto armazena a chave em um arquivo de backup na pasta `keys` caso você precise usá-la futuramente.

## Estrutura do Projeto

- `FernetHasher`: Classe que implementa as funcionalidades de criptografia e descriptografia utilizando Fernet.
- `BaseModel`: Classe base que manipula o salvamento e a recuperação de registros do "banco de dados".
- `Password`: Classe que representa uma senha, contendo informações como domínio e data de criação.
- Script Principal: Um script interativo onde você pode optar entre salvar uma nova senha ou visualizar uma senha existente.

## Instalação e Configuração

1. **Clonar o Repositório**
   ```bash
   git clone <(https://github.com/devkapassos/senhas_com_criptografia)>
   cd <senhas_com_criptografia>
2. Instalar Dependências Este projeto utiliza a biblioteca cryptography. Instale-a usando pip:
   pip install cryptography
3. Configurar Diretórios Certifique-se de que as pastas keys e db existam na raiz do projeto para armazenar as chaves e os dados.

## Como Usar
1. Criar e Salvar uma Nova Senha
Ao iniciar o programa, escolha a opção 1 para salvar uma nova senha.
Se não houver uma chave criada, uma nova chave será gerada e salva no diretório keys.
Insira o domínio e a senha a serem criptografados e armazenados.
2. Recuperar uma Senha Existente
Escolha a opção 2 para recuperar uma senha.
Insira o domínio e a chave de criptografia associada.
Se a senha existir para o domínio, ela será descriptografada e exibida.

## Exemplo de Uso
Digite 1 para salvar uma nova senha ou 2 para ver uma senha: 1
Dominio: exemplo.com
Senha: minhaSenhaSegura123
Digite 1 para salvar uma nova senha ou 2 para ver uma senha: 2
Dominio: exemplo.com
Key: <chave_criptografia>

## Observações Importantes
Segurança da Chave: A chave de criptografia deve ser mantida em um local seguro, pois é necessária para recuperar as senhas.
Gerenciamento de Arquivo de Chave: Depois de arquivar a chave, mova-a para um local seguro e remova o arquivo da pasta keys para evitar acessos indesejados.

## Tecnologias Utilizadas
- Python
- Cryptography (biblioteca)
