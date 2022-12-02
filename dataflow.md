# QUICKSTART

```bash
# Create a playground
mvn archetype:generate \
    -DarchetypeGroupId=org.apache.beam \
    -DarchetypeArtifactId=beam-sdks-java-maven-archetypes-examples \
    -DarchetypeVersion=2.43.0 \
    -DgroupId=org.example \
    -DartifactId=word-count-beam \
    -Dversion="0.1" \
    -Dpackage=org.apache.beam.examples \
    -DinteractiveMode=false
    
# Run wordcount example locally with Direct Runner
mvn compile exec:java \
  -Dexec.mainClass=org.apache.beam.examples.WordCount \
  -Dexec.args="--inputFile=/var/log/README --output=output/counts" \
  -Pdirect-runner

# Use remote Dataflow Runner to run wordcount example
mvn compile exec:java \
  -Dexec.mainClass=org.apache.beam.examples.WordCount \
  -Dexec.args="--gcpTempLocation=gs://BUCKET/staging/ \
    --output=gs://BUCKET/output/wordcount \
    --runner=DataflowRunner \
    --region=us-central1" \
  -Pdataflow-runner
```

Ref:  https://beam.apache.org/get-started/quickstart-java/
