# Dataflow

[TOC]

## QUICKSTART

Get [sample code](https://github.com/apache/beam/tree/master/examples/java) first:

```bash
mvn archetype:generate \
    -DarchetypeGroupId=org.apache.beam \
    -DarchetypeArtifactId=beam-sdks-java-maven-archetypes-examples \
    -DarchetypeVersion=2.43.0 \
    -DgroupId=org.example \
    -DartifactId=word-count-beam \
    -Dversion="0.1" \
    -Dpackage=org.apache.beam.examples \
    -DinteractiveMode=false

cd word-count-beam
```

Various ways to run the same wordcount quickstart demo:

```bash
# Example1: Use Dataflow Runner to run wordcount example with default arguments
mvn compile exec:java \
      -Dexec.mainClass=org.apache.beam.examples.WordCount \
      -Dexec.args="--output=output/wordcount"
      
# Example2: Use Direct Runner to run wordcount example locally
mvn compile exec:java \
  -Dexec.mainClass=org.apache.beam.examples.WordCount \
  -Dexec.args="--inputFile=/var/log/README --output=output/counts" \
  -Pdirect-runner

# Example3: Use Dataflow Runner to run wordcount example with custom arguments
mvn compile exec:java \
  -Dexec.mainClass=org.apache.beam.examples.WordCount \
  -Dexec.args="--gcpTempLocation=gs://BUCKET/staging/ \
    --output=gs://BUCKET/output/wordcount \
    --runner=DataflowRunner \
    --region=us-central1" \
  -Pdataflow-runner
```

Ref:  https://beam.apache.org/get-started/quickstart-java/

## Sample Code Examples

- https://github.com/GoogleCloudPlatform/DataflowTemplates
- https://github.com/apache/beam/tree/master/examples
