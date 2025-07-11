# 🔗 Connecting Applications to Oracle NoSQL Database Cloud Service

Welcome to the **Oracle University** module on application connectivity with Oracle NoSQL DB Cloud.  
By the end of this lesson, you'll understand:

- 🧾 Required credentials
- 💻 How to connect from Java, Python, Node.js, Go, and .NET
- 🌍 Data regions and service endpoints

---

## 🔐 Required Credentials

To connect any application to Oracle NoSQL DB Cloud Service, you need:

| Credential                 | Description                                    |
|---------------------------|------------------------------------------------|
| `Tenancy OCID`            | Unique ID of your Oracle Cloud tenancy         |
| `User OCID`               | Unique ID of the user making the connection    |
| `Private Key (PEM)`       | Used for signing requests                      |
| `Fingerprint`             | Identifies the public key uploaded to Oracle   |
| `Passphrase (optional)`   | Protects the private key                       |

> These are available in your **OCI Console**.

---

## ⚙️ General Steps to Connect

1. **Collect credentials** from OCI Console
2. **Create a Handle object** using the credentials and service endpoint
3. **Verify connection** to ensure no errors
4. **Send requests** using the handle

---

## ☕ Java Application

### ✅ Prerequisites

- JDK 1.8
- Oracle NoSQL Java SDK

### 🔧 Two Approaches

1. **Pass credentials directly in code**
   ```java
   SignatureProvider provider = new SignatureProvider(tenancyId, userId, privateKey);
   NoSQLHandleConfig config = new NoSQLHandleConfig(Region.ASHBURN, provider);
   NoSQLHandle handle = NoSQLHandleFactory.createNoSQLHandle(config);
   ```
2. Use a config file
- Place OCI config in default path (~/.oci/config)
- Java picks it up automatically
  ```java
  SignatureProvider provider = new SignatureProvider(); // uses default config
  ```

## 🐍 Python Application
### ✅ Prerequisites
- Python 2.7.5 / 3.5+
- Oracle NoSQL Python SDK

### 🔧 Two Approaches
- Credentials in code
  ```python
  provider = SignatureProvider(tenancy, user, key, fingerprint, passphrase)
  config = NoSQLHandleConfig("us-ashburn-1", provider)
  handle = NoSQLHandle(config)
  ```
- Use default config file
  ```python
  provider = SignatureProvider()  # uses ~/.oci/config
  ```
  
## 🟩 Node.js Application
### ✅ Prerequisites
- Node.js 12+
- Node Package Manager (NPM)

### 🔧 Three Approaches
- Inline credentials in code
  ```js
  const client = new NoSQLClient({
    region: "us-ashburn-1",
    auth: {
      tenancyId, userId, fingerprint, privateKeyFile, passphrase
    }
  });
```
- Use default OCI config file
  ```js
  const client = new NoSQLClient({ configFile: "~/.oci/config", profile: "DEFAULT" });
  ```
- Use IAMCredentialProvider for custom sources
  ```js
  const provider = new IAMCredentialProvider(customKeyStore);
  const client = new NoSQLClient({ region: "us-ashburn-1", auth: provider });
  ```

## 🧱 Go Application
### ✅ Prerequisites
- Go 1.1+
- Set PATH to Go binary
- Install Oracle NoSQL Go SDK (via Go module)

### 🔧 Connection Example
  ```go
  config := nosqldb.ConfigFromFile("~/.oci/config", "DEFAULT")
  config.Region = "us-ashburn-1"
  client := nosqldb.NewClient(config)
  ```

## 🧱 .NET Application
### ✅ Prerequisites
- .NET 5.0 or .NET Core 3.1+
- Oracle NoSQL .NET SDK

### 🔧 Two Approaches
1. Inline config
  ```csharp
  var config = new NoSQLConfig {
      Region = "us-ashburn-1",
      TenancyId = "...",
      UserId = "...",
      KeyFile = "...",
      Fingerprint = "..."
  };
  ```
2. Use default config file
  - Located in ~/.oci/config
  - Load using default SDK behavior

## 🌍 Data Regions & Service Endpoints

| 🌐 Region Name | 🌎 Identifier      | 🔗 Endpoint URL                                              |
|----------------|--------------------|--------------------------------------------------------------|
| Ashburn        | `us-ashburn-1`     | `https://nosql.us-ashburn-1.oci.oraclecloud.com`            |
| Frankfurt      | `eu-frankfurt-1`   | `https://nosql.eu-frankfurt-1.oci.oraclecloud.com`          |
| Tokyo          | `ap-tokyo-1`       | `https://nosql.ap-tokyo-1.oci.oraclecloud.com`              |

- **Data Region**: The geographic location where your Oracle Cloud resources reside.
- **Service Endpoint**: The region-specific API access URL used to interact with Oracle NoSQL Database Cloud Service.

> 🧭 **Important:** Always configure your application handle with the correct **region endpoint** to ensure successful and secure connectivity.

---

## ✅ Summary

| Topic               | Key Information                                                       |
|---------------------|------------------------------------------------------------------------|
| 🔐 Credentials       | Tenancy ID, User ID, PEM Private Key, Fingerprint, (optional) Passphrase |
| 🧰 SDKs Available    | Java, Python, Node.js, Go, .NET                                       |
| 📦 Handle Object     | Main interface for sending queries and requests to NoSQL DB           |
| 🌍 Endpoints         | Region-based service URLs required for connecting to the cloud        |

---

## 🙌 Thanks for Learning!

This concludes the **Oracle NoSQL Database Cloud – Application Connectivity** module.  
You're now fully equipped to securely connect your applications and build powerful, scalable solutions with **Oracle Cloud**! 🚀
