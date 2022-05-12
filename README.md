Lua 5.4 Reference Manual

2 – Basic Concepts

    2.1 – Values and Types
    
       .Lua is a dynamically typed language. This means that variables do not have types; only values do. There are no type definitions in the language. All values carry their own type.
       
       .All values in Lua are first-class values. This means that all values can be stored in variables, passed as arguments to other functions, and returned as results.

        .There are eight basic types in Lua: [ nil, boolean, number, string, function, userdata, thread,  table ]
        
                        .nil:    The type nil has one single value, nil, whose main property is to be different from any other value; it often represents                                    the absence of a useful value.
                        
                        .boolean:The type boolean has two values, false and true. Both nil and false make a condition false; they are collectively called                                        false values. Any other value makes a condition true. Despite its name, false is frequently used as an alternative to                                       nil, with the key difference that false behaves like a regular value in a table, while a nil in a table represents an                                       absent key.
                        
                        .number:  The type number represents both integer numbers and real (floating-point) numbers, using two subtypes: integer and float.                                     Standard Lua uses 64-bit integers and double-precision (64-bit) floats, but you can also compile Lua so that it uses                                        32-bit integers and/or single-precision (32-bit) floats. The option with 32 bits for both integers and floats is                                            particularly attractive for small machines and embedded systems. (See macro LUA_32BITS in file luaconf.h.)

                                      Unless stated otherwise, any overflow when manipulating integer values wrap around, according to the usual rules of                                         two-complement arithmetic. (In other words, the actual result is the unique representable integer that is equal                                             modulo 2n to the mathematical result, where n is the number of bits of the integer type.)

                                      Lua has explicit rules about when each subtype is used, but it also converts between them automatically as needed                                           (see §3.4.3). Therefore, the programmer may choose to mostly ignore the difference between integers and floats or to                                       assume complete control over the representation of each number.
