# FleetCheck – Build Systems Lab

This project is intentionally incomplete. Follow the worksheet in the order given.

Expected final application output:

```
FleetCheck 1.0
Vehicles loaded: 4
Vehicles requiring service: 2
Average mileage: 37000 km
```

Do not copy the solution POM. The objective is to observe how each build change alters the result.

1-
[ERROR] /C:/Users/carol/Desktop/Faculdade/3ºano/QualidadeSoftware/worksheet4/FleetCheck_Starter/src/main/java/pt/upt/fleetcheck/App.java:[11,9] cannot find symbol
  symbol:   class ObjectMapper
  location: class pt.upt.fleetcheck.App

O erro é causado pelo seguinte import no App.java: import com.fasterxml.jackson.databind.ObjectMapper

2- É um melhor porque o projeto agora pode compilar com sucesso e o Maven pode proceder para a fase de teste.

4- O plugin Maven Shade modifica o JAR padrão, criando um JAR executável e independente.

5- O Maven Wrapper elimina a suposição implícita de que o Maven já está instalado e configurado corretamente na máquina do desenvolvedor.

7- O SBOM contém componentes que não foram declarados explicitamente nas dependências originais do projeto, porque o Maven também inclui dependências transitivas.

8.1- error: package com.fasterxml.jackson.databind does not exist
A dependência em falta é jackson-databind.
