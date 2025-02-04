## Objeto de Política de Grupo (GPO) - Windows Server 2016 📜

Implementação de Mensagem de Boas Vindas! ☕

## 🥑 Aplicação de Script Logon (Boas Vindas) 

### Script ps1
```
<comando_de_instalação>
```
---
#### Conversão ps1 -> exe (ps2exe)
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
