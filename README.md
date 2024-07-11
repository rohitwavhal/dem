## Running the Web Server

### Linux

#### Build and Run

To build and run the web server on Linux:

1. **Build**:
   ```sh
   go build -o main ./cmd/backend-challange/main.go
1. **Run**:
   ```sh
   ./main

### Windows

#### Build and Run

To build and run the web server on Windows:

1. **Build**:
   ```sh
   go build -o main.exe .\cmd\backend-challange\main.go
1. **Run**:
   ```sh
   .\main.exe

## Using the API
Once the web server is running, you can interact with it using curl commands:
1. curl -F 'file=@/path/to/matrix.csv' "localhost:8080/echo"
2. curl -F 'file=@/path/to/matrix.csv' "localhost:8080/invert"
3. curl -F 'file=@/path/to/matrix.csv' "localhost:8080/flatten"
4. curl -F 'file=@/path/to/matrix.csv' "localhost:8080/sum"
5. curl -F 'file=@/path/to/matrix.csv' "localhost:8080/multiply"

Replace /path/to/matrix.csv with the actual path to your CSV file when using these curl commands to test the different operations of the web service.
   
# League Backend Challenge

In main.go you will find a basic web server written in GoLang. It accepts a single request _/echo_. Extend the webservice with the ability to perform the following operations

Given an uploaded csv file
```
1,2,3
4,5,6 
7,8,9
```

1. Echo (given)
    - Return the matrix as a string in matrix format.
    
    ```
    // Expected output
    1,2,3
    4,5,6
    7,8,9
    ``` 
2. Invert
    - Return the matrix as a string in matrix format where the columns and rows are inverted
    ```
    // Expected output
    1,4,7
    2,5,8
    3,6,9
    ``` 
3. Flatten
    - Return the matrix as a 1 line string, with values separated by commas.
    ```
    // Expected output
    1,2,3,4,5,6,7,8,9
    ``` 
4. Sum
    - Return the sum of the integers in the matrix
    ```
    // Expected output
    45
    ``` 
5. Multiply
    - Return the product of the integers in the matrix
    ```
    // Expected output
    362880
    ``` 

The input file to these functions is a matrix, of any dimension where the number of rows are equal to the number of columns (square). Each value is an integer, and there is no header row. matrix.csv is example valid input.  

Run web server
```
go run .
```

Send request
```
curl -F 'file=@/path/matrix.csv' "localhost:8080/echo"
```

## What we're looking for

- The solution runs
- The solution performs all cases correctly
- The code is easy to read
- The code is reasonably documented
- The code is tested
- The code is robust and handles invalid input and provides helpful error messages
