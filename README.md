Zeta
====

If you need in depth docs, go to: http://GraisenEdwards.github.io

_Documentation_
---------------
Variables are declared by using their keywords, or by using `var`, where Zeta will **infer** the **most optimal** type

Their keywords are:

* `var`: (A data type that is **inferred** (e.g. In, `var a equ 9; a equ a div 23;`, `a` would be a `fi32 8` which is the **smallest**, **fastest** and **most convenient*** (Has the most room to grow or shrink) type that will work))
* `bit`: (An **one bit** integer generally used as a _boolean_)
* `i8`: (An **eight bit** signed _integer_)
* `i16`: (A **sixteen bit** signed _integer_)
* `i32`: (A **thirty-two bit** signed _integer_)
* `i64`: (A **sixty-four bit** signed _integer_)
* `u8`: (An **eight bit** unsigned _integer_)
* `u16`: (A **sixteen bit** unsigned _integer_)
* `u32`: (A **thirty-two bit** unsigned _integer_)
* `u64`: (A **sixty-four bit** unsigned _integer_)
* `f8`: (An **eight bit** floating point _number_)
* `f16`: (A **sixteen bit** floating point _number_)
* `f32`: (A **thirty-two bit** floating point _number_)
* `f64`: (A **sixty-four bit** floating point _number_)
* `fi8`: (An **eight bit** fixed point _number_)
* `fi16`: (A **sixteen bit** fixed point _number_)
* `fi32`: (A **thirty-two bit** fixed point _number_)
* `fi64`: (A **sixty-four bit** fixed point _number_)
* `achar`: (An **eight bit** ASCII _character_)
* `char`: (A **sixteen bit** unicode _character_)
* `astring`: (A **collection** of `achar`s)
* `string`: (A **collection** of `char`s)

Operations and symbols can change and manipulate data using their symbols

Their symbols are:

* `;`: (End lines of code)
* `(` and `)`: (Group expressions, also used to enclose arguments for functions)
* `[` and `]`: (Make arrays)
* `{` and `}`: (Group code(Blocks), and also goes after conditional statments (e.g. if, while, ect.))
* `add`: (Add two numbers. AKA Add)
* `sub`: (Subtract two numbers. AKA Subtract)
* `mul`: (Multiply two numbers. AKA Multiply)
* `div`: (Divide two numbers. AKA Divide)
* `mod`: (Modulo two numbers. AKA Modulo)
* `not`: (Boolean not)
* `or`: (Boolean or)
* `and`: (Boolean and)
* `xor`: (Boolean xor)
* `nor`: (Boolean nor)
* `nand`: (Boolean nand)
* `xnor`: (Boolean xnor)
* `bnot`: (Bitwise not)
* `bor`: (Bitwise or)
* `band`: (Bitwise and)
* `bxor`: (Bitwise xor)
* `bnor`: (Bitwise nor)
* `bnand`: (Bitwise nand)
* `bxnor`: (Bitwise xnor)

Conditionals, loops and gotos control the code flow

Their keywords are:

* `goto: label`: (Sets `label` as a valid `goto` spot)
* `goto label`: (Goes to `label` (Still valid even if `goto: label` is defined after `goto label` is used))
* `if`: (If a condition is met, continue, if the condition is not, skip to the end of the block)
* `else`: (Used with if. If the condition is not met, continue. If the condition is met, skip over this block)
* `while`: (While the condition is met, repeat the block over and over)
* `skip`: (Skips this cycle of `while`, and is the same as `goto`ing to the end of the code block)
* `break`: (Breaks out of `while`, and is the same as `goto`ing out of `while`)
* `fun`: (Declares a function. AKA Function)
* `ret`: (Returns a value from functions and also exits the functions, but requires a type. AKA Return)

Object-Oriented Programming is a way of programming and abstraction

Their keywords are:

* `class`: (Creates an object)
* `enum`: (Creates a new type that can be compared. AKA Enumatration)
* `extends`: (Makes a "template" for a class where the developer can override/create objects)
* `prv`: (Anything modified with `prv`, can only be used inside the class. AKA Private)

Memory management is the way you can mess with memory

You can do this with:

* `static`: (Makes the variable `static` is used on persistent)
* `sizeof`: (Gives you the size of a variable in bits)
* `copyto`: (Copies the value of `x` in `*x copyto *y` to `y`)
* `setto`: (Sets the value of `x` in `1 copyto *x` to `1`)

Other:

* `import`: (Imports a file, as if the contents of the file is at the location of the `import`)
* `type`: (Get the type of a variable in `Type`(`enum`) form)
* `typeset`: (Sets the type of the targeted varible)
* `const`: (Makes anythong modified with `const` is immutable)
* `alias`: (Sets an alias (Mostly used to reassign operations like turning `add` to `+`))
* `//`: (Linelong comment)
* `/*`: (Start of custom comment)
* `*/`: (End of custom comment)

_Usage_
-------
* `//`: `code; // Comment`
* `/*`, `*/`: `/* Comment */ code; /* More comments */`
* `var`: `var varName;` or `var varName equ valueToInitTo;`
* `bit`, `i8`, `i16`, `i32`, `i64`, `u8`, `u16`, `u32`, `u64`, `f8`, `f16`, `f32`, `f64`: `varType varName;` or `varType varName equ valueToInitTo;`
* `fi8`, `fi16`, `fi32`, `fi64`: `varType bitsBeforeDecimal varName;` or `varType bitsBeforeDecimal varName equ valueToInitTo;` (Although, if you want to cast to a fixed point number, you would need to do something like `typeset value fixedPointType bitsBeforeDecimal;` as technically things like `fi8 2` are types while `fi8` is not)
* `;`: `code;`
* `(`, `)`: `functionName(paramType params);`
* `[`, `]`: `f16 varName 3 equ [thing1, thing2, thing3];`
* `{`, `}`, `fun`: `fun functionName(paramType params) { code; }`
* `ret`: `fun functionName() { i32 varName equ 1; ret i32 varName; }`
* `add`, `sub`, `mul`, `div`, `mod`: `valueOrVar op valueOrVar`
* `not`: `not bit`
* `or`, `and`, `xor`, `nor`, `nand`, `xnor`: `bit1 op bit2`
* `bnot`: `bnot num`
* `bor`, `band`, `bxor`, `bnor`, `bnand`, `bxnor`: `num1 op num2`
* `goto:`, `goto`: `goto label; i8 varName equ 9; goto: label;`, label will not exist because `goto` skipped it
* `if`, `else`: `if(booleanVarName) { /* Code if true */ } else { /* Code if false */ }`
* `while`, `skip`, `break`: `while(booleanVarName) { if(booleanVarName) { skip; } break; }`
* `class`, `extends`, `prv`: `class ClassName extends otherClassName { prv fi32 8 varName equ 4.3; fun funName() { varName equ varName add 1; } } ClassName classNameName equ ClassName(); classNameName.varName equ classNameName.varName add 1;` The first instance of `varName equ classNameName.varName add 1;` does not give errors because `varName` is inside the class, but the second instance **does** give an error because `varName` is outside the class
* `enum`: `enum EnumName { THING1 = 3764.985, THING2 = 6 typeset i16, THING3 }`
* `static`: `fun functionName() { static f64 varName equ 0; varName equ varName add 1; }` where after every invocation of the function increments `varName` by one
* `sizeof`: `fun functionName(string param) { ret string sizeof param; }`
* `copyto`, `setto`: `f64 varName1 equ 6.4; f64 varName2 equ 0; 7 setto *varName1; *varName1 copyto *varName2;`
* `type`, `typeset`: `i8 varName1 equ 7; if(type varName1 equ Type.i8) { f16 varName2 equ varName1 typeset f16; }`
* `const`: `const i16 constName equ 84; constName equ 328;` will give an error because you tried to modify a constant
* `alias`: `alias true 1; alias false 0; alias long i64;`
* `import`: `import file.zt; i8 varName equ 7;` will be the same as the contents of `i8 varName equ 7` appended to file.zt

_Quirks_
--------
* When using `var`, `var` will never choose floating points, because floating points are slightly slower. If you would like to have floating points when using var, put `varoverride fi8 f8; varoverride fi16 f16; varoverride fi32 f32; varoverride fi64 f64;` at the top of you're program
* If you would like to change the type of a variable, you can do something like `typeToConvertTo varName;` or `typeToConvertTo varName equ valueToInitTo;`
* When declaring arrays, do it like `varType varName arraySize equ [thing1, thing2, thing3, ...];` or `var varName arraySize;` or some other combination
* Zeta does not follow order of operations, it goes left to right, unless the expression is enclosed in parentheses
* If you reinitialise a variable, it will be ignored (e.g. `i32 variableName equ 0; i32 variableName equ 1;` where the second instance will be ignored)
