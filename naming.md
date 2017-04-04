# Nomes

Esta seção descreve as convenções gerais de nomenclatura que dizem respeito à capitalização de caracteres, escolha de palavras e diretrizes sobre o uso de abreviações e acrônimos.

## Convenções Gerais

Escolha nomes de identificadores facilmente legíveis que favoreçam a legibilidade sobre a brevidade.

```C#
    // Bom.
    public object GetWindow();

    // Ruim.
    public object GetWin();
```

## Capitalização

Para diferenciar palavras em um identificador capitalize a primeira letra de cada palavra do nome do identificador. Apenas duas convenções de capitalização são aceitas, dependendo do identificador utilizado:

- PascalCase
- camelCase

### PascalCase

A convenção _PascalCasing_ deve ser utilizada para todos os identificadores exceto nomes de parâmetros e variáveis de escopo local ou privadas, incluindo acrônimos com mais de duas letras em tamanho.

- PropertyDescriptor
- HtmlTag
- JsonSerializer

Acrônimos com duas letras devem ser mantidos capitalizados:

- IOStream

### camelCase

A convenção _camelCasing_ deverá ser utilizada apenas para nomes de parâmetros e variáveis de escopo local ou privadas. Nomes de identificados que utilizam esta convenção e que iniciam com acrônimos deverão ter todas as suas letras em minúsculo.

- propertyDescriptor
- htmlTag
- jsonSerializer

Acrônimos com duas letras devem não são mantidos capitalizados:

- ioStream

### Caracteres Especiais

Não utilize _underscores_ ou qualquer outro tipo de caractére não alfanumérico.

```C#
    // Bom.
    string windowName;

    // Ruim.
    string window_name;
```

### Acrônimos

Utilize apenas os acrônimos amplamente aceitos por sua cultura ou que sejam parte do domínio de negócio da aplicação.

```C#
    // Bom.
    class IOStream;
    class Cpf;

    // Ruim.
    class FSUtil;
```

> CPF é um acrônimo para Cadastro de Pessoa Física, um típo de registro de identificação utilizado no Brasil.

### Abreviações de Tipo

Não abrevie os nomes com a finalidade de identificar seu tipo ou visibilidade de acesso.

```C#
    // Bom.
    class Foo {
        int length;
        string name;
    };

    // Ruim.
    class CFoo {
        int iLength;
        string f_name
    };
```

### Uso de Nomes Específicos da Linguagem

Use nomes semânticamente interessantes e evite utilizar palavras reservadas da linguagem.

```C#
    // Bom.
    public abstract int GetLength();

    // Ruim.
    public abstract int GetInt();
```

### Namespaces

Use nomes que sugiram grandes agrupamentos de funcionalidade, como em `System.Collections`. Considere utilizar o seguinte padrão:

```Plain
    <organização>.<componente>
```

onde _componente_ contém um ou mais identificadores separados por ponto:

```Plain
    namespace Microsoft.AspNet.Identity.Core { }
    namespace Ninject.Web.Common { }
```

### Classes e Structs

O nomes de _Classes_ e _Structs_ devem estar no singular e utilizar palavras substântivas simples ou frases substântivas.

```C#
    // Bom.
    class Stream { }
    class Dictionary { }
    class ConnectionProvider { }

    // Ruim.
    class Streamer { }
    class Dictionaries { }
    class ConnectionProviders { }
```

### Interfaces

Use adjetivos ou substântivos para nomes de _Interfaces_. Interfaces têm seu nome abreviado com a letra I respeitando-se as regras de capitalização.

```C#
    // Substântivos.
    interface IComponent { }
    interface ICustomAttributeProvider { }

    // Adjetivos.
    interface IPersistable { }
```

### Methods

Use verbos ou frases verbais que indiquem a ação executada e evite redundâncias de nomes.

```C#
    // Bom.
    class Person {
        public void Save() { }
    }

    // Ruím.
    class Person {
        public void SavePerson() { }
    }
```

### Type Members

#### Properties

Missing.

#### Events

Missing.

### Parameters

Missing.

## Tabela de Referência

Identificador | Visibilidade | Casing | Exemplo
--- | --- | --- | ---
Namespace | * | PascalCase | `namespace System.Security`
Type | * | PascalCase | `class StreamReader`
Interface | * | PascalCase | `interface IEnumerable`
Method | * | PascalCase | `virtual string ToString() { }`
Property | * | PascalCase | `int Length { get; set; }`
Event | * | PascalCase | `event EventHandler Exited;`
Delegate | * | PascalCase | `delegate int Exited(string message);`
Field | `public, internal, protected` | PascalCase | `public TimeSpan InfiniteTimeout;`
Field | `private` | camelCase | `private TimeSpan InfiniteTimeout;`
Enum value | * | PascalCase | `enum FileMode { Read, Append }`
Parameter | * | camelCase | `public static int ToInt32(string value);`

## Referência

[Microsoft .Net Framework Design Guidelines - Naming Guidelines](https://msdn.microsoft.com/en-us/library/ms229002(v=vs.110).aspx)
