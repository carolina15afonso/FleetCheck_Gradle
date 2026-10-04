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

1- [ERROR] /C:/Users/carol/Desktop/Faculdade/3ºano/QualidadeSoftware/worksheet4/FleetCheck_Starter/src/main/java/pt/upt/fleetcheck/App.java:[11,9] cannot find symbol
  symbol:   class ObjectMapper
  location: class pt.upt.fleetcheck.App

O erro é causado pelo seguinte import no App.java: import com.fasterxml.jackson.databind.ObjectMapper

2- É um erro melhor porque o projeto agora pode compilar com sucesso e o Maven pode prosseguir para a fase de teste.

4- O plugin Shade cria o artefacto fleetcheck-1.0.0-all.jar, empacota as dependências necessárias dentro dele e adiciona pt.upt.fleetcheck.App como a main class no manifest. Deste modo é criado um JAR executável.

5- O Maven Wrapper elimina a suposição implícita de que o Maven já está instalado e configurado corretamente na máquina do desenvolvedor.

7- O SBOM contém componentes que não foram declarados explicitamente nas dependências originais do projeto, porque o Maven também inclui dependências transitivas.

8.1- error: package com.fasterxml.jackson.databind does not exist
A dependência em falta é jackson-databind.

8.2- jackson-databind é uma dependência direta porque foi declarada em build.gradle. jackson-core e jackson-annotations são dependências transitivas de jackson-databind.
A mudança do Maven para o Gradle não alterou as dependências da aplicação. As mesmas dependências diretas e transitivas são necessárias. Apenas o sistema de compilação e a sintaxe usada para declarar essas dependências foram alterados.

8.3- A configuração do arquivo JAR foi alterada para adicionar pt.upt.fleetcheck.App como a classe principal e para incluir as dependências de tempo de execução dentro do JAR.

8.4- O Gradle Wrapper remove a suposição de que o Gradle esteja instalado no computador. O projeto fornece o seu próprio Gradle Wrapper, permitindo que a compilação seja executada de forma consistente usando o arquivo gradlew.bat.
