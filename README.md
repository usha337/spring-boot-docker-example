# spring-boot-docker-example

# Java and MongoDB Example

This example app shows how to package a Spring Boot application with Docker. See [Add Docker to Your Spring Boot Application][blog-post] to see how it was built.

## Prerequisite

- **Java 8**: If you don’t have Java 8, you can install OpenJDK. Instructions are found on the  [OpenJDK website](https://openjdk.java.net/install/).
- **Docker** - We recommend https://www.docker.com/products/docker-desktop[Docker Desktop]
- **Okta Developer Account**: Go to [the Okta website](https://developer.okta.com/signup/) and sign up for a free developer account, if you haven’t already.

> [Okta](https://developer.okta.com/) has Authentication and User Management APIs that reduce development time with instant-on, scalable user infrastructure. Okta's REST API and makes it easy for developers to authenticate, manage, and secure users + roles in any application.

* [Getting Started](#getting-started)
* [Create OIDC App](#create-a-new-oidc-app-in-okta)
* [Configure the Resource Server](#configure-the-resource-server)
* [Run the Resource Server](#run-the-resource-server)
* [Help](#help)
* [License](#license)

## Getting Started

To install this example application, run the following commands:

```bash
git clone https://github.com/oktadeveloper/spring-boot-docker-example.git
```

## Create a New OIDC App in Okta

If you don't have an Okta developer account, please [create one](https://developer.okta.com/signup/). Then, create a new OIDC app on Okta:

1. Log in to your developer account, navigate to **Applications** > **Add Application**.
2. Select **Web** > **Next**.
3. Give the application a name
4. The rest of the default values will work. Click  **Done**.

## Configure the Resource Server

You need to add the Client ID and Secret from newly created Okta application, and the Issuer URI from your Okta account to the `src/main/resources/application.properties` file. To find your Issuer URI, go to **API** -> **Authorizaiton Servers**.

```properties
okta.oauth2.issuer=https://{yourOktaUrl}/oauth2/default
okta.oauth2.client-id={yourClientId}
okta.oauth2.client-secret={yourClientSecret}
```

## Run the Application

To run the Spring Boot application

```bash
./mvnw spring-boot:run
```

See the [blog post] for details on building the Docker container and managing your configuration.

## Help

Please post any questions as comments on the [blog post] or post them to Stack Overflow with the `okta` tag.

## License

Apache 2.0, see [LICENSE](LICENSE).

[blog-post]: https://developer.okta.com/blog/2019/12/27/spring-boot-deploy-docker
