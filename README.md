# Renomeando-varias-planilhas-ao-mesmo-tempo
Este repositório contém um script PowerShell simples e eficiente que renomeia diversos arquivos `.xlsx` de uma pasta, adicionando um sufixo personalizado no final do nome.

## 🧠 Cenário de uso

# Você tem vários arquivos como: 

- relatorio_vendas.xlsx
- extrato_funcionarios.xlsx
- alelo_gastos.xlsx


# E quer que eles fiquem assim:


- relatorio_vendas_jun25.xlsx
- extrato_funcionarios_jun25.xlsx
- alelo_gastos_jun25.xlsx

## 📝 Como usar
Abra o PowerShell (Windows+s e procure por powershell).

Navegue até a pasta onde estão suas planilhas:
→ importante colocar o cd e aspas antes de inserir o caminho

cd "C:\caminho\da\pasta"

Dê enter.
```

Depois copie e cole o Script abaixo:

## 💻 Script PowerShell

```powershell
Get-ChildItem -Filter *.xlsx | ForEach-Object {
    $nomeOriginal = $_.BaseName
    $extensao = $_.Extension
    $novoNome = $nomeOriginal + "_jun25" + $extensao
    Rename-Item -Path $_.FullName -NewName $novoNome
}
