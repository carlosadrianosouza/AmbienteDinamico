name: Execução Manual

on:
  workflow_dispatch:
    inputs:
      ambiente:
        description: 'Qual ambiente você quer rodar?'
        required: true
        default: 'stg'
        type: choice
        options:
          - stg
          - staging
          - production
      mensagem_customizada:
        description: 'Uma mensagem extra para o log'
        required: false
        default: 'Nenhuma mensagem'
        type: string

jobs:
  run_pipeline:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout do código
        uses: actions/checkout@v3

      - name: Exibir os inputs
        run: |
          echo "Ambiente selecionado: ${{ github.event.inputs.ambiente }}"
          echo "Mensagem customizada: ${{ github.event.inputs.mensagem_customizada }}"
          
      - name: Executar script para o ambiente
        run: |
          echo "Executando script para o ambiente ${{ github.event.inputs.ambiente }}"
          # Aqui você colocaria o comando real para rodar seu script, ex:
          # npm run deploy-${{ github.event.inputs.ambiente }}
          # ou um comando de shell que use o ambiente