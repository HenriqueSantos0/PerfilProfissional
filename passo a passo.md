# Processo de criação de pilhas na AWS com o cloudformation utilizando. 
### Criar ususario na AWS e dar privilegios de adm.
- Navegue até IAM.
- Usuarios.
- Criar novo Usuario.
- Definir senha automatica.
- Definir preferencias de grupo com adm.
- Manter todas as outras configuração como padrão.
## LEMBRAR DE BAIXAR O CSV QUE É GERADO APÓS CRIAR O USUARIO.
### Criar a chave para acesso ao cluster.
- Navegue até Kay Pair.
- Create Key.
- Defina o nome da chave e o formato(.pem ou .ppk).
### conferir se a IAC está em bucket AWS e conferir o caminho até esse bucket.
- Navegiue até S3.
- Abra o bucket e confira.
- Caso não tenha um bucket com a IAC, ele deve ser criado e o arquivo deve ser subido para o bucket.
### Abrir o terminal no computador.
- Executar o comando _aws configure_.
- **Ir no csv baixado na criação do usuario e copiar as informações de ID e secret Key.**
- **Copie as informações e cole quando forem solicitadas.**
- Executar o comando _aws s3 ls_ para conferir se a configuração funcionou.
- O erro mais comum de acontecer é nas configuração onde existe uma flaha da assinatura, então é necessario repetir o processo de configuração com calma.
- Se existir outro erro, busque solução.
- Executar o comando _aws cloudformation create-stack --stack-name "[1]" --template-url http://[2].s3.amazonaws.com/[3] --parameters ParameterKey=KeyName,ParameterValue='[4]' --capabilities CAPABILITY_IAM_
- **onde:** 
- [1] - Deve ser substituuido pelo nome que o ususario deseja para a pilha que está sendo criada.
- [2] - Deve ser substituuido pelo nome do bucket que contem a IAC.
- [3] - Deve ser substituuido pelo nome do arquivo da IAC junto com a estensão do arquivo.
- [4] - Deve ser substituuido pelo nome da chave para acesso ao cluster.
### O comando ira criar um cluter de acordo com as informação da IAC.
### Vá até a plataforma da AWS, navegue até o ClodFOrmation e confira o processo.
