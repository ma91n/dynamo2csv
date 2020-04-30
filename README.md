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
$ dynamo2csv --help
Usage of ./dynamo2csv:
  -c, --columns string                       DynamoDB Column names order for using csv output
      --expression-attribute-names string    Attribute names
      --expression-attribute-values string   Attribute values
      --filter-expression string             Filter Expression
      --profile string                       AWS Profile Name
  -t, --table string                         DynamoDB Table name that is export target
```
