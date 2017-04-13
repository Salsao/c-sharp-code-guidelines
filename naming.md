# 1. Nomes

<!-- TOC -->

- [1. Nomes](#1-nomes)
    - [1.1. Convenções Gerais](#11-convenções-gerais)
    - [1.2. Capitalização](#12-capitalização)
        - [1.2.1. PascalCasing](#121-pascalcasing)
        - [1.2.2. camelCasing](#122-camelcasing)
    - [1.3. Nomenclatura de Tipos](#13-nomenclatura-de-tipos)
        - [1.3.1. Namespaces](#131-namespaces)
        - [1.3.2. Classes, Structs e Enums](#132-classes-structs-e-enums)
        - [1.3.3. Interfaces](#133-interfaces)
        - [1.3.4. Methods](#134-methods)
            - [1.3.4.1. Method Parameters](#1341-method-parameters)
        - [1.3.5. Properties e Fields](#135-properties-e-fields)
        - [1.3.6. Events](#136-events)
            - [1.3.6.1. Event Handlers](#1361-event-handlers)
            - [1.3.6.2. Event Arguments](#1362-event-arguments)
    - [1.4. Caracteres Especiais](#14-caracteres-especiais)
    - [1.5. Acrônimos](#15-acrônimos)
    - [1.6. Abreviações](#16-abreviações)
    - [1.7. Uso de Nomes Específicos da Linguagem](#17-uso-de-nomes-específicos-da-linguagem)
    - [1.8. Tabela de Referência](#18-tabela-de-referência)
    - [1.9. Referência](#19-referência)

<!-- /TOC -->

## 1.1. Convenções Gerais

Evite abreviações e escolha nomes de identificadores que favoreçam a legibilidade do código.

```C#
    // Bom.
    public object GetWindow();

    // Ruim.
    public object GetWin();
```

## 1.2. Capitalização

Para diferenciar palavras em um identificador capitalize a primeira letra de cada palavra do nome do identificador. Apenas duas convenções de capitalização são aceitas, dependendo do identificador utilizado:

- PascalCase
- camelCase

### 1.2.1. PascalCasing

A convenção _PascalCasing_ deve ser utilizada para todos os identificadores exceto nomes de parâmetros e variáveis de escopo local ou privadas, incluindo acrônimos com mais de duas letras em tamanho.

- PropertyDescriptor
- HtmlTag
- JsonSerializer

Acrônimos com duas letras devem ser mantidos capitalizados:

- IOStream

### 1.2.2. camelCasing

A convenção _camelCasing_ deverá ser utilizada apenas para nomes de parâmetros e variáveis de escopo local ou privadas. Nomes de identificados que utilizam esta convenção e que iniciam com acrônimos deverão ter todas as suas letras em minúsculo.

- propertyDescriptor
- htmlTag
- jsonSerializer

Acrônimos com duas letras devrão estar em minúsculo:

- ioStream

## 1.3. Nomenclatura de Tipos

### 1.3.1. Namespaces

Utilize substântivo singular para os nomes de _Namespaces_ que sugiram agrupamentos de funcionalidades, como em `System.Collections`. Considere utilizar o seguinte padrão:

```Plain
    <organização>.<componente>
```

onde _componente_ contém um ou mais identificadores separados por ponto:

```Plain
    namespace Microsoft.AspNet.Identity.Core { }
    namespace Ninject.Web.Common { }
```

Utilize

### 1.3.2. Classes, Structs e Enums

Utilize substântivo singular para os nomes de _Classes_, _Structs_ e _Enums_.

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

### 1.3.3. Interfaces

Utilize adjetivo ou substântivo singular para nomes de _Interfaces_. Interfaces têm seu nome sufixado com a letra "_I_" respeitando-se as regras de capitalização.

```C#
    // Substântivos.
    interface IComponent { }
    interface ICustomAttributeProvider { }

    // Adjetivos.
    interface IPersistable { }
```

### 1.3.4. Methods

Use verbos ou frases verbais que indiquem a ação executada e evite redundâncias de palavras.

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

#### 1.3.4.1. Method Parameters

_Method Parameters_ são expostos na documentação em ferramentas do tipo _intellisense_ ou de localização de símbolos, por isso utilize nomes descritivos que indiquem o significado do parâmetro e não o seu tipo.

Utilize adjetivo ou substântivo singular para nomes de _Method Parameters_, plural quando coleções.

### 1.3.5. Properties e Fields

Utilize adjetivo ou substântivo para nomes de _Properties_ e _Fields_.

```C#
    public int Age { get; set; }
```

Pluralize o nome de _Properties_ do tipo coleção, como _Lists_, _Arrays_ e _Sets_.

```C#
    public IList<string> Roles { get; set; }
```

Utilize frases afirmativas para _Properties_ do tipo _boolean_.

```C#
    public bool CanSeek { get; set; }
```

Considere nomear a _Property_ com o mesmo nome de seu tipo.

```C#
    enum Color { Black, White };
    class Control {
        public Color Color { get; set; }
    }
```

O uso de _Fields_ é limitado ao escopo `private`. Para armazenamento de valores nos escopos `protected`, `internal` e `public` utilize apenas _Properties_.

### 1.3.6. Events

_Events_ estão relacionados a ações que ocorream ou ainda ocorrerão. Use verbos ou frases verbais flexionados temporalmente para para indicar o momento em que a ação ocorre para nomes de _Events_.

```C#
    event EventHandler<PaintingEventArgs> Painting;
    event EventHandler<PaintedEventArgs> Painted;
```

#### 1.3.6.1. Event Handlers

_Event Handlers_ (_delegates_ utilizados com tipos de eventos) são sufixados com a frase "_EventHandler_" e seus dois parâmetros devem ser nomeados "_sender_" e "_e_".

```C#
    delegate void PaintingEventHandler(object sender, PaintingEventArgs e);
    delegate void PaintedEventHandler(object sender, PaintedEventArgs e);
```

#### 1.3.6.2. Event Arguments

_Types_ que representam argumentos específicos de _Events_ devem possuir o nome do _Event_ sufixado com a frase "_EventArgs_".

```C#
    class PaintingEventArgs : EventArgs {}
    class PaintedEventArgs : EventArgs {}
```

## 1.4. Caracteres Especiais

Não utilize _underscores_ ou qualquer outro tipo de caractere não alfanumérico.

```C#
    // Bom.
    string windowName;

    // Ruim.
    string window_name;
```

## 1.5. Acrônimos

Utilize apenas os acrônimos amplamente aceitos por sua cultura ou que sejam parte do domínio de negócio da aplicação.

```C#
    // Bom.
    class IOStream;
    class Cpf;

    // Ruim.
    class FSUtil;
```

> CPF é um acrônimo para Cadastro de Pessoa Física, um típo de registro de identificação utilizado no Brasil.

## 1.6. Abreviações

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

## 1.7. Uso de Nomes Específicos da Linguagem

Use nomes semânticamente interessantes e evite utilizar palavras reservadas da linguagem.

```C#
    // Bom.
    public abstract int GetLength();

    // Ruim.
    public abstract int GetInt();
```

## 1.8. Tabela de Referência

Identificador | Escopo | Casing | Gramática | Exemplo
--- | --- | --- | --- | ---
`Namespace` | * | `PascalCase` | substantivo | `namespace Ninject.Web.Common`
`Class` | * | `PascalCase` | substântivo | `class BinaryReader`
`Struct` | * | `PascalCase` | substântivo | `struct Book`
`Enum` | * | `PascalCase` | substântivo | `enum FileMode { Append, Create }`
`Interface` | * | `PascalCase` | adjetivo ou substântivo sufixado com "I" | `interface IEnumerable`
`Method` | * | `PascalCase` | verbo | `byte[] Read(int count)`
`Parameter` | | `camelCase` |  adjetivo ou substântivo | `long Seek(int offset, SeekOrigin origin)`
`Property` | * | `PascalCase` | adjetivo ou substântivo, plural para coleções | `long Length { get; set; }`
`Field` | private | `camelCase` | adjetivo ou substântivo, plural para coleções | `List<User> users`
`Event` | * | `PascalCase` | verbo flexionado temporalmente | `event EventHandler<PaintedEventArgs> Painted`
`Delegate` | * | `PascalCase` | nome do evento sufixado com _EventHandler_ | `delegate int PaintedEventHandler(object sender, PaintedEventArgs e)`

## 1.9. Referência

[Microsoft .Net Framework Design Guidelines - Naming Guidelines](https://msdn.microsoft.com/en-us/library/ms229002(v=vs.110).aspx)
