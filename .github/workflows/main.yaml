name: Deploy Manual por Ambiente

on:
  workflow_dispatch:
    inputs:
      ambiente:
        description: 'Selecione o ambiente'
        required: true
        default: 'STG'
        type: choice
        options:
          - STG
          - PRD

jobs:
  deploy:
    runs-on: ubuntu-latest
    environment: ${{ inputs.ambiente }}

    steps:
      - name: Checkout do código
        uses: actions/checkout@v3

      - name: Mostrar ambiente selecionado
        run: echo "🚀 Ambiente selecionado: ${{ inputs.ambiente }}"

      - name: Mostrar variável do environment
        run: echo "🔧 APP_ENV: $APP_ENV"
        env:
          APP_ENV: ${{ vars.APP_ENV }}

      - name: Usar segredo do environment
        run: echo "🔐 A chave da API foi lida com sucesso!"
        env:
          API_KEY: ${{ secrets.API_KEY }}
