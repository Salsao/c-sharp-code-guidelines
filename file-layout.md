# Organização

## Pastas e arquivos

Tipos devem ser armazenadas em um arquivo com o o nome do tipo declarado e com a extensão `.cs`.

Um arquivo poderá conter apenas um tipo declarado e deverá ser armazenado numa estrutura de pastas que identifique seu _namespace_. Estas pastas poderão conter uma ou mais partes do namespace à partir da raiz do projeto.

Tipos aninhados (_nested types_) ou declarados dentro de outros tipos (_inner types_) são permitidos e nestes casos o arquivo deverá possuir o nome do tipo declarado externo declarado no _namespace_.

### Exemplo

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
