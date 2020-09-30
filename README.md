# Teste DevOps
Descrição:
Este repositório contém um simples website com um fluxo de trabalho, sendo iniciado após atualização do repositório do GitHub, que logo em seguida inicializa o GitHub Actions, no qual executa um template de infraestrtura do CloudFormation AWS, onde provisionar o ambiente e deploy da aplicação que estará rodando em um container Docker dentro da infraestrutura da AWS Cloud.

# Topologia 
![image](https://user-images.githubusercontent.com/55636741/94643648-b5606500-02bd-11eb-9865-0c4fa9a32270.png)

# Pré-requisitos 
* Você criará um novo repositório template no GitHub, a partir do repositorio: > https://github.com/jerryjmp/TesteIA.git 

![image](https://user-images.githubusercontent.com/55636741/94646712-38d18480-02c5-11eb-8384-224a06c17b89.png) 
* Após a criação do repostório no passo acima, é necessário alterar o arquivo: infraaws-template-ia.yml no bloco: 
                
```sh
De:   
                sudo git clone https://github.com/jerryjmp/TesteIA.git
                sudo mv /git/Dockerfile /TesteIA
                sudo cd /TesteIA
                sudo systemctl start docker
                sudo docker build -t app_hello_world /TesteIA/
```
            
    Para:       
```sh           sudo git clone https://github.com/Sua_Conta/Seu_Repositorio.git
                sudo mv /git/Dockerfile /Seu_Repositorio
                sudo cd /Seu_Repositorio
                sudo systemctl start docker
                sudo docker build -t app_hello_world /Seu_Repositorio/  
```
* Crie dois secrets no GitHub para a chave de acesso em seu repositório do GitHub em Settings > Secrets. Como alternativa, você pode criar esses secrets no nível da organização do GitHub e conceder acesso aos secrets para seu novo repositório.

    Crie um secrets chamado AWS_ACCESS_KEY_ID contendo o valor AccessKeyId do seu usuário da conta AWS.
    Crie um secrets denominado AWS_SECRET_ACCESS_KEY contendo o valor SecretAccessKey do seu usuário da conta AWS.

![image](https://user-images.githubusercontent.com/55636741/94648782-9f58a180-02c9-11eb-9d86-088b782b55e8.png) 

* Realize uma atualização no arquivo index.php, deixando conforme a linha abaixo:  
  ```sh
  <?php echo "<p>Hello World!</p>"; ?>  
   ``` 

# Deploy
 * Realize a atualização do repositório com os comandos abaixo:
 ```sh
$ cd /path_repositorio_tempalte
$ git add . 
$ git commit -m "Deploy"
$ git push 
```
* Aguardar a criação da infraestrutura e publicação do Website.
* Para validar o pipeline e criação do website, basta entrar na sua console da AWS, e validar a criação da instância EC2 e abrir o DNS IPv4 no seu browser e resultado será conforme abaixo: 

![image](https://user-images.githubusercontent.com/55636741/94654286-39711780-02d3-11eb-9403-104bc417129e.png)

# Monitação
* Será utilizada a ferramenta Amazon CloudWatch com as métricas padrão para o website Hello World. 




























[//]: # (These are reference links used in the body of this note and get stripped out when the markdown processor does its job. There is no need to format nicely because it shouldn't be seen. Thanks SO - http://stackoverflow.com/questions/4823468/store-comments-in-markdown-syntax)


   [dill]: <https://github.com/joemccann/dillinger>
   [git-repo-url]: <https://github.com/joemccann/dillinger.git>
   [john gruber]: <http://daringfireball.net>
   [df1]: <http://daringfireball.net/projects/markdown/>
   [markdown-it]: <https://github.com/markdown-it/markdown-it>
   [Ace Editor]: <http://ace.ajax.org>
   [node.js]: <http://nodejs.org>
   [Twitter Bootstrap]: <http://twitter.github.com/bootstrap/>
   [jQuery]: <http://jquery.com>
   [@tjholowaychuk]: <http://twitter.com/tjholowaychuk>
   [express]: <http://expressjs.com>
   [AngularJS]: <http://angularjs.org>
   [Gulp]: <http://gulpjs.com>

   [PlDb]: <https://github.com/joemccann/dillinger/tree/master/plugins/dropbox/README.md>
   [PlGh]: <https://github.com/joemccann/dillinger/tree/master/plugins/github/README.md>
   [PlGd]: <https://github.com/joemccann/dillinger/tree/master/plugins/googledrive/README.md>
   [PlOd]: <https://github.com/joemccann/dillinger/tree/master/plugins/onedrive/README.md>
   [PlMe]: <https://github.com/joemccann/dillinger/tree/master/plugins/medium/README.md>
   [PlGa]: <https://github.com/RahulHP/dillinger/blob/master/plugins/googleanalytics/README.md>
