# dynamo2csv
Export DynamoDB table to CSV

## Installation

```bash
go get -u github.com/laqiiz/dynamo2csv
```

## Usage

All Data

```bash
./dynamo2csv -t <TableName> > out.csv
```

Filter Expression

```bash
./dynamo2csv -t <TableName> \
  -filter-expression 'contains(#ts, :s)' \
  -expression-attribute-values '{":s":{"S":"15:00:00Z"}}' \
  -expression-attribute-names '{"#ts":"timestamp"}' > out.csv
```

## Options

```bash
./dynamo2csv -h
Usage of ./dynamo2csv:
  -c string
        -c is DynamoDB Column names
  -columns string
        -columns is DynamoDB Column names
  -expression-attribute-names string
        Attribute names
  -expression-attribute-values string
        Attribute values
  -filter-expression string
        Filter Expression
  -t string
        -t is DynamoDB Table name that is export target
  -table string
        -table is DynamoDB Table name that is export target
```
