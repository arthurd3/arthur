programa {
  inclua biblioteca Util --> u
  funcao inicio() {
    
    cadeia mapa[5][6]
    inteiro linha=0, coluna=0 , pontos = 0
    inteiro ultimaLinha=0, ultimaColuna=0 , teste = 0 , linha1 , coluna1 ,linha2 , coluna2 ,linha3 , coluna3 , linha4 , coluna4 , x 
    caracter direcao
      linha1 = u.sorteia(1,4)
      coluna1 = u.sorteia(1, 4)
      linha2 = u.sorteia(1,4)
      coluna2 = u.sorteia(1, 4)
      linha3 = u.sorteia(1,4)
      coluna3 = u.sorteia(1, 4)
      linha4 = u.sorteia(1,4)
      coluna4 = u.sorteia(1, 4)
    

  //Preenchendo a mapa de jogo com zeros
    para (inteiro i=0;i<5;i++){
      para (inteiro j=0;j<5;j++){
        mapa[i][j] = "_"
        mapa[i][4] = "_"
        mapa[i][0] = "_"
        
      }
    }
    escreva("ESCOLHA SUA DIFICULDADE: \n 1 : MEDIO \n 2 : DIFICIL \n","\n")
    leia(x)
    limpa()
    se (x==1)
    
    {
      mapa[linha1][coluna1] = "*"
      mapa[linha2][coluna2] = "*"
      mapa[linha3][coluna3] = "*"
      mapa[linha4][coluna4] = "*"
    }
    se (x==2)
    {
      mapa[linha1][coluna1] = "*"
      mapa[linha2][coluna2] = "*"
      mapa[linha3][coluna3] = "*"
      mapa[linha4][coluna4] = "*"
      linha4 = u.sorteia(1,4)
      mapa[linha4][coluna4] = "*"
      linha4 = u.sorteia(1,4)
      mapa[linha4][coluna4] = "*"
      mapa[linha4][coluna4] = "*"
      linha4 = u.sorteia(1,4)
      mapa[linha4][coluna4] = "*"
      linha4 = u.sorteia(1,4)
      mapa[linha4][coluna4] = "*"
    }
    
   
    
    //Definindo a posicao inicial da personagem
    mapa[0][0]= "@"

    //Mostrando a versão inicial do mapa
    para (inteiro i=0;i<5;i++){
      para (inteiro j=0;j<5;j++){
        escreva(mapa[i][j], " ")
      }
    escreva("\n")
    }    

    //Lendo um comando para movimentar a personagem
    enquanto(teste == 0){
      escreva("\nPontos: ",pontos)
      escreva("\nDigite o comando: ")
      leia(direcao)
      limpa()
      //Verificando qual tecla foi pressionada
      escolha(direcao){
        caso "s": 
          se(linha + 1 < 5){
            linha++
            pontos=pontos+50
          }
          pare
        caso "a": 
          se(coluna - 1 >=0 ){
            coluna--
            pontos=pontos+50
          }
          pare
        caso "w": 
          se(linha - 1 >=0 ){
            linha--
            pontos=pontos+50  
          }
          pare
        caso "d": 
          se(coluna + 1 < 5){
            coluna++
            pontos=pontos+50
          }
          
          pare
        caso contrario: 
          pare
      }
      //Momerizando qual foi a última posição que a personagem esteve
      mapa[ultimaLinha][ultimaColuna]="_"
      
      //Definindo a nova posição da personagem no mapa
      mapa[linha][coluna]="@"
      
      
      //Exibindo o mapa de jogo atualizado
       para (inteiro i=0;i<5;i++){
       para (inteiro j=0;j<5;j++){
          escreva(mapa[i][j], " ")

        
      }
        escreva("\n")
        
      }
        ultimaLinha=linha
        ultimaColuna=coluna

      se(linha == linha1 e coluna == coluna1 ou linha == linha2 e coluna == coluna2 ou linha == linha3 e coluna == coluna3 ou linha == linha4 e coluna == coluna4 ou "*"=="@"){
          escreva("GAME OVER","\n")
          teste++
      }
    }
  }    
}

