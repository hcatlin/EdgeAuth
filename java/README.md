# Phenix EdgeAuth Digest Tokens for Java

Easily generate secure digest tokens to use with the Phenix platform without requiring any networking activity.

## Installation

To install the Phenix Edge Authorization Digest Token library with gradle, add the following depencency line to your `build.gradle`:

```Groovy
compile group: 'com.phenixrts.edgeauth', name: 'edge-auth', version: '1.0.0'
```

### Bundled UberJar

To install the Phenix Edge Authorization Digest Token uberjar bundled with all its dependencies, add the following dependency to your `build.gradle`:

```Groovy
compile group: 'com.phenixrts.edgeauth', name: 'edge-auth', version: '1.0.0', clasifier: 'bundle'
```

## Java Example

```Java
import com.phenixrts.edgeauth.TokenBuilder;

// Create a token to access a channel
final String token = new TokenBuilder()
	.withApplicationId("my-application-id")
	.withSecret("my-secret")
	.expiresInSeconds(3600)
	.forChannel("us-northeast#my-application-id#my-channel.1345")
	.build();
```

## Command Line Examples

Display the help information:
```shell script
java -jar build/libs/EdgeAuth-1.0-SNAPSHOT-uberjar.jar --help
```

Create a token for channel access:
```shell script
java -jar build/libs/EdgeAuth-1.0-SNAPSHOT-uberjar.jar --applicationId "my-application-id" --secret "my-secret" --expiresInSeconds 3600 --channel "us-northeast#my-application-id#my-channel.1345"
```