# Projeto AWS Cloudfornation CFN UserData

Nesse projeto foi desenvolvido um modelo de script com base nos dados do usuário para o modelo cloud EC2 usando função FN::base64 para fazer o Bootstrap quando a instâcia por toda usa vez for iniciada na AWS.esta função retorna a representação base64 da string de entrada e passa dados codificados para a instância do EC2 podendo atualizar a nossa configuração para garantir que os scripts de dados do usuário e as diretrizes da entrada em nuvem seja executada
toda vez que reiniciamos nossa instância.
Como referência eu crei uma página da Web como saída para exibir a App Tomcat8 para da ênfase ao projeto.

# EC2 UserData

- CloudFormation & UserData
- Sample:

- UserData:
-   FN::Base64: |
-   #!/bin/bash
-    sudo yum update
-   sudo yum -y erase java0-1.7.0-openjdk.x86_64
-    sudo yum -y install java-1.8.0-openjadk.x86_64
-    sudo yum -y installmjava-1.8.0-openjadk-dev1
-    sudo yum -y install tomcat8
-    service tomcat8 start
-    mkdir /user/share/tomcat8/webapps/ROOT
-    touch /user/share/tomcat8/webapps/ROOTS/index.html
-    echo "Cloud Formation Tomcat8" > /user/share/tomcat8/webapps/

• Podemos usar os dados do usuário no modelo de formação de nuvem para EC2.
• Precisamos usar uma função intrínseca Fn::base64 com os dados do usuário nos modelos CFN.Esta função retorna a representação base64 da string de entrada.Ele passa dados codificados para a instância do EC2.
• Pipe YAML (|): Qualquer texto recuado que se segue deve ser interpretado como um valor escalar com várias linhas, o que significa que o valor deve ser interpretado literalmente de tal maneira que preserve as novas linhas.
• UserData Contras
• Por padrão, os scripts de dados do usuário e as diretrizes da entrada de nuvem são executadas apenas durante o ciclo de inicialização quando iniciamos uma instância.
• Podemos atualizar nossa configuração para garantir que os scripts de dados do usuário e as diretrizes da entrada em nuvem sejam executadas toda vez que reiniciamos nossa instância.(Reboot of servers requimired).
