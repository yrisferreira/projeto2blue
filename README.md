# projeto2blue
//JOGO JOKEMPÔ

let introducao = prompt(" Bem-vindo ao JOKEMPÔ, Pressione [ENTER] para começar.")
console.log
let resposta = "s"

const continuacaoDeJogo = ['s','S','SIM','sim',1]
const possibilidadesDeJogada = ['Pedra', 'Papel', 'Tesoura']
const Resultados = ['GANHOU', 'PERDEU', 'EMPATE']

while (resposta == continuacaoDeJogo[1] || resposta == continuacaoDeJogo[2] || resposta == continuacaoDeJogo[3] || resposta == continuacaoDeJogo[4] || resposta == continuacaoDeJogo[0]) {
  console.clear()

  let numero_de_rodadas = prompt("Quantas vezes você gostaria de jogar?")  
  let pontuacao_computador = 0
  let pontuacao_jogador = 0

  for(i = 1; i <= numero_de_rodadas; i++) {
    let jogada_computador = Math.floor(Math.random() * 3+1)
    console.log(`Rodada ${i}`)
    let jogada = 0
    let jogada_jogador = prompt(" [1]PEDRA [2]PAPEL  [3]TESOURA: ")

    while (jogada_jogador != 1 && jogada_jogador.toLowerCase() != "pedra" && jogada_jogador != 2 && jogada_jogador.toLowerCase() != "papel" && jogada_jogador != 3 && jogada_jogador.toLowerCase() != "tesoura") {
      console.log("RESPOSTA INVÁLIDA!, VAMOS TENTAR NOVAMENTE?")
      console.log
      jogada_jogador = prompt(" [1]PEDRA [2]PAPEL [3]TESOURA: ")
    }

    if (jogada_jogador == 1 || jogada_jogador.toLowerCase() == "pedra") {
      console.log(`Jogador: ${possibilidadesDeJogada[0]}`)
      jogada = 1
    } else if (jogada_jogador == 2 || jogada_jogador.toLowerCase() == "papel") {
      console.log(`Jogador: ${possibilidadesDeJogada[1]}`)
      jogada = 2
    } else if (jogada_jogador == 3 || jogada_jogador.toLowerCase() == "tesoura") {
      console.log(`Jogador: ${possibilidadesDeJogada[2]}`)
      jogada = 3
    }

    if (jogada_computador == 1) {
      console.log(`Computador: ${possibilidadesDeJogada[0]}`)
    } else if (jogada_computador == 2) {
      console.log(`Computador: ${possibilidadesDeJogada[1]}`)
    } else if (jogada_computador == 3) {
      console.log(`Computador: ${possibilidadesDeJogada[2]}`)
    }

    if (jogada == 1 && jogada_computador == 1) {
      console.log(`${Resultados[2]}`)
    } else if (jogada == 1 && jogada_computador == 2) {
      console.log(`${Resultados[1]}`)
      pontuacao_computador++
    } else if (jogada == 1 && jogada_computador == 3) {
      console.log(`${Resultados[0]}`)
      pontuacao_jogador++
    } else if (jogada == 2 && jogada_computador == 1) {
      console.log(`${Resultados[0]}`)
      pontuacao_jogador++
    } else if (jogada == 2 && jogada_computador == 2) {
      console.log(`${Resultados[2]}`)
    } else if (jogada == 2 && jogada_computador == 3) {
      console.log(`${Resultados[1]}`)
      pontuacao_computador++
    } else if (jogada == 3 && jogada_computador == 1) {
      console.log(`${Resultados[1]}`)
      pontuacao_computador++
    } else if (jogada == 3 && jogada_computador == 2) {
      console.log(`${Resultados[0]}`)
      pontuacao_jogador++
    } else if (jogada == 3 && jogada_computador == 3) {
      console.log(`${Resultados[2]}`)
    }
    }
    console.log()
    const final = prompt("Gostaria de ver o resultado? aperte: [ENTER].")
    console.clear()

    if (pontuacao_computador > pontuacao_jogador){
      console.log("VITORIA DO COMPUTADOR ")
      console.log(`Você: ${pontuacao_jogador} \nComputador: ${pontuacao_computador}`)
    } else if (pontuacao_computador < pontuacao_jogador){
      console.log("Urrul, A Vitoria é sua!")
      console.log(`Você: ${pontuacao_jogador} \nComputador: ${pontuacao_computador}`)
    } else if (pontuacao_computador == pontuacao_jogador){
      console.log("EMPATE")
      console.log(`Você: ${pontuacao_jogador} \nComputador: ${pontuacao_computador}`)
  }

  console.log()
  resposta = prompt("Vamos repetir o jogo? [1]SIM [2]NÃO ")
}
console.log(" Game over, obrigada!")
