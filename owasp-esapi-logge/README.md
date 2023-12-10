**OWASP Enterprise Security API (ESAPI)**
 - ESAPI (The OWASP Enterprise Security API) is a free, open source, web application security control library that makes it easier for programmers to write lower-risk applications.
 - The ESAPI libraries are designed to make it easier for programmers to retrofit security into existing applications.
 - ESAPI defines a org.owasp.esapi.Logger interface that represents the common logging operations such as trace, debug, info, warn, and error.

**Maven Dependency:**
```
<!-- https://mvnrepository.com/artifact/org.owasp.esapi/esapi -->
<dependency>
    <groupId>org.owasp.esapi</groupId>
    <artifactId>esapi</artifactId>
    <version>2.2.3.1</version>
</dependency>
```

**Example of how we can use the OWASP ESAPI Logger in Java code:**

```
import org.owasp.esapi.ESAPI;
import org.owasp.esapi.Logger;

// Assuming you have an ESAPI Logger instance
Logger esapiLogger = ESAPI.getLogger("YourLoggerName");

// Instead of using the standard logger, use the ESAPI Logger with proper encoding
esapiLogger.info("Response Body -> {}", ESAPI.encoder().encodeForHTML(response.body()));
```
ESAPI.encoder().encodeForHTML(response.body()). This ensures that the content of response.body() is properly encoded for HTML, preventing HTML injection attacks in logs.

**Ref:** 
- https://owasp.org/www-project-enterprise-security-api/
- https://mvnrepository.com/artifact/org.owasp.esapi/esapi/2.2.3.1
