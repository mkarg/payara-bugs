# [PAYARA-5602](https://github.com/payara/Payara/issues/5602)

1. Install Payara Full CE 5.2022.1

2. Enable security on *all* http listeners:

```
asadmin set configs.config.server-config.network-config.protocols.protocol.http-listener-1.security-enabled=true
asadmin set configs.config.server-config.network-config.protocols.protocol.http-listener-2.security-enabled=true
```

3. Build the EAR using Maven:

```bash
mvn clean package
```
4. Deploy the EAR:

```bash
asadmin deploy ear/target/ear-1.0.0.ear
```

5. The following will happen:

```bash
remote failure: Error occurred during deployment: Exception while preparing the app. Please see server.log for more details.
Exception while invoking class org.glassfish.webservices.WebServicesDeployer prepare method : java.lang.RuntimeException
Command deploy failed.
```
