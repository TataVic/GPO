# Implementação de Mensagem de Boas Vindas! ☕



## 🥑 Aplicação de Script Logon (Boas Vindas) 
### Script ps1
- Carrega bibliotecas necessárias para criar a interface gráfica (System.Windows.Forms, System.Drawing, PresentationFramework).
- Obtém a hora atual e determina uma saudação dinâmica (Bom dia, Boa tarde, Boa noite).
- Cria um formulário fixo com título e ícone personalizado.
- Adiciona um Label para exibir um aviso.
- Exibe uma imagem  abaixo do texto.
- Impede o redimensionamento da janela, removendo os botões de minimizar/maximizar.
- Exibe a janela como um diálogo modal, forçando o usuário a visualizá-la antes de prosseguir.

<p align="center">
  <img src="https://github.com/user-attachments/assets/11b09763-5bb6-4445-bb4b-736d30519b8e" width="500px;" />

</p>


---
#### Conversão ps1 -> exe (ps2exe) 
    🍄 {Execute como administrador o PowerShell }
- Irá precisar instalar o ps2exe:
  ```
  Install-Module -Name ps2exe -Scope CurrentUser
  ```
- Precisa de módulos sem restrição temporariamente só para o console em aberto:
 ```
  Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
```
- Para a conversão de script (entre a aspas coloque o caminho do arquivo):
  ```
  Invoke-PS2EXE -inputFile "seu_script.ps1" -outputFile "seu_script.exe"
  ```
---

### Windows Server :
Tenha o aqruivo ps1 em seu servidor e faça todo o processo de conversão em um caminho raiz de seu servidor.
- Lembre de colocar o executável e as imagens em uma pasta compartilhada com permissões de leitura;
- As imagens e executáveis irão ter que estar localmente em pastas raízes do servidor.
  
---
### Windows 10/11 :
Para forçar a aplicação da GPO, certifique estar vinculada a um link corretamente na máquina e usuário cliente.
```
gpupdate /force
```
e ver se foio aplicada para o devido cliente:
```
gpresult -v || gpresult /v
```

### GPO:
- Vá em Gerenciamento de Política de Grupo;
- Crie a GPO e edite;
```
   Configuração do Computador → Preferências → Configurações do Windows → Arquivos
```
- Crie um arquivo com o caminho de origem e o caminho que irá receber;
```
   Configuração do Computador → Preferências → Configurações do Windows → Registros
```
- Crie um registro com Hive (HKEY_LOCAL_MACHINE || Chave (SOFTWARE\Microsoft\Windows\CurrentVersion\Run) || Tipo de valor (REG_SZ) || Dados de valor (Caminho da imagem)
```
   Configuração do Usuário → Políticas → Scripts (Logon/Logoff)
```
- Crie na aba de script e coloque o caminho raiz do servidor que possue do executável. 
