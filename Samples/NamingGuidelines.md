# CODING STANDARDS

## Naming Guidelines

Learn to follow a standard naming design pattern for any programming language. Following a standard naming convention while coding can be a significant contribution to the project.

A single project is shared across many developers. Beyond consistency of form, names of framework elements must be easily understood and must convey the function of each component.

The objective of the article is to showcase a uniform naming practice that results in names that give instant insight to developers.

### Contents

-   Capitalization Conventions
-   General Naming Conventions
-   Names of Assemblies and DLLs
-   Names of Namespaces
-   Names of Classes, Structs, and Interfaces
-   Names of Type Members
-   Naming Parameters

### Capitalization Conventions

✔️ Use PascalCasing for all class members, type, and namespaces.

✔️ Use camelCase for the variable names.

#### Examples

**Identifier   Casing   Example**

```
Namespace    Pascal   namespace Test\
Type         Pascal   public class ClassName\
Interface    Pascal   public interface IInterface\
Property     Pascal   public void Test()\
Event        Pascal   public event EventHandler\
Enum value   Pascal   public Enum TestEnum\
Parameter    Camel    public string testVariable
```

❌ DO NOT capitalize each word in compound words as most compound words are treated as single words.

#### Example
```
**//Compound word "Callback"**

Pascal     => Callback\
Camel      => callback\
NOT TO USE => CallBack
```
### General Naming Conventions

It describes general naming conventions that correlate to word selection, guidelines on using contractions and acronyms, and instructions on how to dodge practicing language-specific names.

✔️ Choose simple identifier names.
```
"**VerticalAlignment** "is more readable name than "**AlignmentVerticle**".
```

✔️ Support readability over compactness.
```
"**CanMoveHorizontally**" is better than "**CanMoveXAxis**"
```

❌ DO NOT use "_," "-," or any other nonalphanumeric characters to separate names.

```
"**newVariable**" is better than "**new_var**" or "**new-var**"
```

❌ DO NOT use reserved language keywords as names.
```
**int, string, List** are some examples of reserved keywords.
```

❌ DO NOT use abbreviations.
```
"**GetCopyData**" is better than "**GetCpData**"
```

### Names of Assemblies and DLLs

✔️ Name DLLs according to the following pattern:
```
<CompanyName>.<ComponentName>.dll
```

✔️ Name DLLs features according to the following design:
```
<CompanyName>.<ComponentName>.<FirstFeature>\
<CompanyName>.<ComponentName>.<SecondFeature>

**Packaged DLL**\
<CompanyName>.<ComponentName>.dll
```

### Names of Namespaces

✔️ Prefix namespace names with a company name to avoid duplicates.
```
namespace CompanyName.Test {...}
```

✔️ Use PascalCasing.
```
namespace TestNamespace {...}
```

✔️ Use plural namespace names
```
"**Collections**" is better than "**Collection"\
**"**Tests**" is better than "**Test"**
```

### Names of Classes, Structs, and Interfaces

✔️ Use PascalCasing.
```
public class HelloWorld {...}
```

✔️ Append the name of the base class at the end of the derived class name. It provides information about the base class as well.
```
"**IndexOutOfRangeException**" has base class name i.e. "**Exception**"
```

❌ DO NOT prefix class names with "C."
```
**Avoid**\
public class CHelloWorld {...}
```

✔️ Prefix interface names with "I" like "ITest."
```
public interface IHelloWord {...}
```

✔️ Prefix generic types with "T" like <TSession>.
```
public void TestMethod<TSession> {...}
```

❌ DO NOT use an "Enum" suffix in enum type names.
```
**Avoid\
public enum HelloWorldEnum {...}**

**Recommended\
public enum HelloWorld {...}**
```

### Names of Type Members

✔️ Give a verb or verb phrase.
```
**//String class**\
public class String {\
  public int CompareTo(...);\
  public string[] Split(...);\
  public string Trim();\
}
```

✔️ Property name should be same as its type.
```
public enum Test {...}\
public class Testing{\
   public Test Test{ get {...} set {...} }\
}
```

✔️Use PascalCasing for field names.

✔️ Use the parameters "sender" and "e" in event handlers.
```
ClickedEventHandler(object sender, ClickedEventArgs e);
```

❌ DO NOT use a prefix "g_" or "s_" to indicate global or static fields.


### Naming Parameters

✔️ Use camelCasing.

✔️ Provide descriptive parameter names.

✔️ Give names based on a parameter's function rather than type.


                                ## Thank you for reading.
