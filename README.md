# sentry-jboss-module
Custom Handler module for using Sentry.io in JBoss (also known as Wildfly)

## Instructions
1. Add the `io.sentry` module (io/sentry/main folder) from this repository in the JBoss modules folder
2. Added the custom handler below to the `standalone.xml` or `domain.xml` (or use the JBoss Management console)
```xml
<custom-handler name="SENTRY" class="io.sentry.jul.SentryHandler" module="io.sentry">
    <level name="WARN"/>
</custom-handler>
```
3. Set the DSN in a `SENTRY_DSN` environment variable or in a `sentry.dsn` system property
4. Assign the handler to the root logger or the log category of your choice
5. Enjoy!

