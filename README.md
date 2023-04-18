# Docker e GO
## Fase 01

<details>
  <summary>
    <strong>
      Informações do desafio
    </strong>
  </summary>

  Esse desafio é muito empolgante principalmente se você nunca trabalhou com a linguagem Go!


  Você terá que publicar uma imagem no docker hub. Quando executarmos:

  ```
  docker run <seu-user>/fullcycle
  ```

  Temos que ter o seguinte resultado: `Full Cycle Rocks!!`


  Se você perceber, essa imagem apenas realiza um print da mensagem como resultado final, logo,
  vale a pena dar uma conferida no próprio site da Go Lang para aprender como fazer um "olá mundo".


  Lembrando que a Go Lang possui imagens oficiais prontas, vale a pena consultar o [Docker Hub](https://hub.docker.com/_/golang).

  1. A imagem de nosso projeto Go precisa ter menos de 2MB =)
  2. Suba o projeto em um **repositório Git remoto** e coloque o link da imagem que subiu no Docker Hub.
  3. Compartilhe o link do repositório do Git remoto para corrigirmos seu projeto.

  Divirta-se!

</details>

<details>
  <summary>
    <strong>
      Notas sobre o desafio
    </strong>
  </summary>

  Criando a imagem apartir do arquivo Dockerfile e rodando para testar;
  ```
  docker build -t fullcycle .

  docker run fullcycle
  ```

  Determinando um tag local para subir para o Docker hub;

  ```
  docker tag fullcycle davidrogger/fullcycle
  docker push davidrogger/fullcycle
  ```

  # Sobre Dockerfile

  Pesquisando para atingir o tamanho mínimo necessário de 2mb, descobri(nunca estudei sobre go, comecei alguns dias, mas não muito afundo) que uma das grandes vantagens do Go é a possibilidade de compilação e usarmos o binário que ele gera seria a melhor abordagem para atingir esse valor de 2mb gerando a imagem do Docker, então pesquisei um pouco sobre, e encontrei um tutorial no youtube, sobre como gerar uma imagem com menor custo, no canal do [devtopics](https://www.youtube.com/watch?v=S12ohWcVfHQ), usando a imagem scratch do docker.

  Para gerar o arquivo bin foi usado o parametro;
  ```
  CGO_ENABLED=0 GOOS=linux go build -a -installsuffix cgo -o bin .
  ```

</details>

#
[RESPOSITÓRIO DOCKER HUB](https://hub.docker.com/r/davidrogger/fullcycle)

