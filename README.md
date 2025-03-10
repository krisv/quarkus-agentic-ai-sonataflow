# sonataflow-ai-agents

This project uses Quarkus, the Supersonic Subatomic Java Framework.
If you want to learn more about Quarkus, please visit its website: https://quarkus.io/ .

## Running the application in dev mode

Make sure you have Java 17+ installed and your JAVA_HOME system property set.

Also update the src/main/resources/application.properties file to include your own OpenAI key.

You can run your application in dev mode that enables live coding using:
```shell script
./mvnw quarkus:dev
```

After starting up in dev mode, you can access the Dev UI at http://localhost:9000/q/dev/

Locate the Serverless Workflow Tools card and click on Workflow Instances to open up the embedded Serverless Workflow console

### Agent

The agent can be triggered by sending a 'request' event with the item identifier and a question.
Click on the Workflow Definitions tab in the central panel, and click the 'Trigger Cloud Event' button.
Fill in 'request' as event type and the following body:
```json
{
    "identifier": "ITEM-0001",
    "request": "Why has my item not been delivered yet?"
}
```
You can look at how the agent executed in the Workflow Instances view.
You should see that ITEM-0001 has a target date before the current date (which is hardcoded in the demo).