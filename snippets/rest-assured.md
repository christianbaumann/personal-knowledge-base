# REST Assured Snippets
http://rest-assured.io

```java
import static io.restassured.RestAssured.*;

import io.restassured.builder.RequestSpecBuilder;
import io.restassured.specification.*;
import org.junit.jupiter.api.BeforeAll;
import org.junit.jupiter.api.Test;

public class RestAssuredTriesTest {

    private static RequestSpecification requestSpec;

    @BeforeAll
    public static void createRequestSpecification() {

        requestSpec = new RequestSpecBuilder().
                setBaseUri("https://finologee.com").
                build();
    }

    @Test
    public void requestContactPage() {

        String responseString = given().
                spec(requestSpec).
                when().
                get("/contact/").
                then().
                assertThat().
                statusCode(200)
                .extract()
                .asString();

        System.out.println(responseString);
    }
}
```