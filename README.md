# Gradle Basic Project

A beginner Java project that demonstrates how to make HTTP requests to a REST API using the [OkHttp](https://square.github.io/okhttp/) library, built and managed with Gradle.

---

## What This Project Does

- Prints a welcome message to the console
- Loops and prints numbers 1 through 5
- Makes a real HTTP GET request to the [Fake Store API](https://fakestoreapi.com/)
- Prints the JSON response of product #1 to the console

**Sample Output:**
```
Hello and welcome!
i = 1
i = 2
i = 3
i = 4
i = 5

{
  "id":1,
  "title":"Fjallraven - Foldsack No. 1 Backpack",
  "price":109.95,
  ...
}
```

---

## Tech Stack

| Tool | Purpose |
|---|---|
| Java | Programming language |
| Gradle | Build tool and dependency management |
| OkHttp 4.12.0 | HTTP client library for making API requests |
| JUnit 5 | Testing framework |

---

## Prerequisites

Make sure you have the following installed before running the project:

- **JDK 11 or higher** — [Download here](https://adoptium.net/)
- **Git** — [Download here](https://git-scm.com/)

You do **not** need to install Gradle separately — the project includes a Gradle Wrapper (`gradlew`) that handles it.

---

## Getting Started

### 1. Clone the repository
```bash
git clone https://github.com/your-username/GradleBasicProject.git
cd GradleBasicProject
```

### 2. Run the project directly
```bash
# Mac/Linux
./gradlew run

# Windows
gradlew run
```

### 3. Build a standalone JAR
```bash
# Mac/Linux
./gradlew clean build

# Windows
gradlew clean build
```

### 4. Run the JAR
```bash
java -jar .\build\libs\GradleBasicProject-1.0-SNAPSHOT.jar
```

> **Note:** The JAR is built as a fat JAR (uber JAR), meaning all dependencies including OkHttp are bundled inside it. You can share this single file and run it anywhere Java is installed.

---

## Project Structure

```
GradleBasicProject/
├── src/
│   └── main/
│       └── java/
│           └── org/example/
│               └── Main.java        # Main application entry point
├── build.gradle                     # Gradle build configuration
├── gradlew                          # Gradle wrapper script (Mac/Linux)
├── gradlew.bat                      # Gradle wrapper script (Windows)
└── README.md
```

---

## Key Concepts Demonstrated

**OkHttp Client** — A simple, efficient HTTP client used to send a GET request to a public REST API and read the response.

**Builder Design Pattern** — The `Request` object is constructed using `Request.Builder`, a common Java pattern that lets you chain configuration methods before building the final object.

**Try-with-resources** — The `Response` object is opened inside a `try(...)` block, ensuring the network connection is always properly closed after use.

**Fat JAR / Uber JAR** — The Gradle `jar` task is configured to bundle all runtime dependencies into a single executable JAR file.

---

## API Used

This project hits the **Fake Store API**, a free public API for practice and testing:

```
GET https://fakestoreapi.com/products/1
```

No API key or authentication required.

---
## Next thing to learn, Json parsing to Java Object (Serialisation and Deserialisation)
Right now, our code print the API response as a raw JSON string.
This is just text. We can't do anything useful with it like product.getPrice() or product.getTitle(). 
That's where JSON Parsing Libraries comes in.
### The Main Players
**Gson - by Google**
The most beginner friendly.

**Moshi - By Square (same people who made OkHttp)**
More modern than Gson, works really well with OkHttp since they're from the same company. Slightly less beginner tutorials available.

**Jackson - By FasterXML**
The most powerful and widely used in enterprise/production backends. Spring Boot uses it by default. A bit more complex to set up.
