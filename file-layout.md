# 1. Organização

<!-- TOC -->

- [1. Organização](#1-organização)
    - [1.1. Pastas e arquivos](#11-pastas-e-arquivos)
        - [1.1.1. Exemplo](#111-exemplo)
    - [1.2. Classes](#12-classes)

<!-- /TOC -->

## 1.1. Pastas e arquivos

Tipos devem ser armazenadas em um arquivo com o o nome do tipo declarado e com a extensão `.cs`.

Um arquivo poderá conter apenas um tipo declarado e deverá ser armazenado numa estrutura de pastas que identifique seu _namespace_. Estas pastas poderão conter uma ou mais partes do namespace à partir da raiz do projeto.

Tipos aninhados (_nested types_) ou declarados dentro de outros tipos (_inner types_) são permitidos e nestes casos o arquivo deverá possuir o nome do tipo declarado externo declarado no _namespace_.

### 1.1.1. Exemplo

Dada a seguinte classe:

```C#
namespace SomeCompany.SomeApp.Data.Repository
{
    public class FooRepository
    {
    }
}
```

seu arquivo deverá estar alocado em uma das seguintes maneiras:

```Plain
/SomeCompany/SomeApp/Data/Repository/FooRepository.cs
/SomeCompany.SomeApp/Data/Repository/FooRepository.cs
/SomeCompany.SomeApp.Data/Repository/FooRepository.cs
/SomeCompany.SomeApp.Data.Repository/FooRepository.cs
```

normalmente sendo a primeira pasta o nome do arquivo de projeto.

## 1.2. Classes

Membros de classe deverão ser organizados conforme o tipo do membro e sua visibilidade de seguinte forma:

```C#
namespace SomeCompany.SomeApp.Data.Repository
{
    public class FooRepository
    {
        // Constants
        // Fields
        // Auto-Properties
        // Delegates
        // Events
        // Enums
        // Constructors
        // Finalizers (Destructors)
        // Complex-Properties
        // Methods
        // Structs
        // Interfaces
        // Classes
    }
}
```

> ___Auto-Properties___ são propriedades com _getter_ ou _setter_ simples, sem implementação de código. ___Complex-Properties___ são propriedades com _getter_ ou _setter_ com implementação de código.

Para cada tipo de membro ordene as declarações por sua visibilidade:

```Plain
public
internal
protected
private
```

Membros estáticos deverão ser declarado acima dos membros não estáticos de mesmo tipo.
