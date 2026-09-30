# ms-config-2026

Configurações da Aula 9 de Sistemas Distribuídos.

Projetos locais: client2026ms (porta 8080) e server2026ms (porta 8888). Este repositório contém somente as configurações que o servidor entrega ao cliente.

| Perfil | Saudação | Nome padrão |
| --- | --- | --- |
| default / dev | Hello | World |
| qa | Ciao | M@rcio |
| perf | ola | Mundo |
| prod | Hola | Mundo |

Inicie primeiro server2026ms e depois client2026ms, executando em cada pasta:

```powershell
.\mvnw.cmd spring-boot:run
```

O cliente está configurado para qa. Consulte http://localhost:8080/greeting ou http://localhost:8080/greeting?name=Marcio.

Para consultar o servidor: http://localhost:8888/client2026ms/qa.

Depois de alterar e publicar o arquivo do perfil no GitHub, atualize o cliente sem reiniciar:

```powershell
Invoke-RestMethod -Method Post -Uri "http://localhost:8080/actuator/refresh" -ContentType "application/json" -Body "{}"
```

A atualização foi testada: Ciao, Mondo! mudou para Ciao, M@rcio! sem reiniciar o cliente.
