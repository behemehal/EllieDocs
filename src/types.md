# Types

- Data Types

  - Numeric
    ```ellie
        int
        float
        double
        byte
    ```
  - String
    ```ellie
        v name : string = "ellie";
    ```
  - Char
    ```ellie
        v firstName : char = 'e';
    ```
  - Cloak
    ```ellie
        v letters : (char, char, char, char, char) = ('e', 'l', 'l', 'i', 'e');
    ```
  - Array
    ```ellie
        v letters : [char, *] = [
            'e',
            'l',
            'l',
            'i',
            'e'
        ];
    ```
  - Collective
    ```ellie
        v letters : {int, char} = {
            1 :'e',
            2 :'l',
            3 :'l',
            4 :'i',
            5 :'e'
        }
    ```
  - Arrow Functions
    ```ellie
        v callingAwesomeness : @(string, int):string = @(name, count):string {
            v awesomenes : string;
            for (element, count) {
                awesomenes += "ellie";
            }
            ret awesomeness;
        }
    ```
  - bool