# Cpp_CustomContainer

Solve an infinite values solution with custom container

## Problem

It is required to map a certain key to multiple values.
The default key must be given at init time.

The client (user of this data structure) should have the following options:
- retreive the key of a certain value
- assign keys to a specific range of values

## Specifications

There must be only one key for a certain value. 
By default, the key of all possible values will be the init key.
The new data type has to be an extension to std::map (if must operate on a private value of type map).
The key and values can be of any type:
- the key implements only the comparable operator "<"
- the value implements only the comparable operator "="
The name of the new data type has to be "CustomMultiValueMap"
The method to retrive will be called "retrive" and which return the key of the type Key
The method to assign will be called "assign" and will have 3 arguments:
- keyBegin of type Key which represents the left key of the interval "\[".
- keyEnd of type Key which represents the right key of the interval ")".
- value of type Value which represents value which must be assigned to the set of keys [keyBegin, keyEnd).


There also must be a method "clear" which will assign all possible values to the default key.
If the keyBegin is < keyEnd, the value must not be assigned

## Example

Key type: integer
Value type: char
The default key is: 1

User retrives key for value "C" and receives key 1

User assigns the key 2 to values "B" to "E"<br>
User retrives key for value "D" and receives key 2<br>
User retrives key for value "E" and receives key 1<br>

User assigns the key 3 to values "C" to "D"<br>
User retrives key for value "A" and receives key 1<br>
User retrives key for value "B" and receives key 2<br>
User retrives key for value "C" and receives key 3<br>
User retrives key for value "D" and receives key 2<br>
User retrives key for value "E" and receives key 1<br>
User retrives key for value "Z" and receives key 1<br>
