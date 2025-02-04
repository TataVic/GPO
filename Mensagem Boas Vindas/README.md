## Objeto de Política de Grupo (GPO) - Windows Server 2016 📜

Implementação de Mensagem de Boas Vindas! ☕

## 🥑 Aplicação de Script Logon (Boas Vindas) 
<details>
<summary>Script ps1</summary>
Detalhes do script:
- 
- 
</details>

```
<comando_de_instalação>
```

Conversão ps1 -> exe (ps2exe)
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


Windows Server :

```
<comando_de_instalação>
```
Windows 10/11 :

```
<comando_de_instalação>
```
