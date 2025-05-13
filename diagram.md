graph TD
    A[User's Browser] --> B[DNS Request: www.foobar.com]
    B --> C[DNS resolves to 8.8.8.8 (A record)]
    C --> D[Server (8.8.8.8)]
    D --> E[Nginx (Web Server)]
    E --> F[App Server]
    F --> G[MySQL Database]
    E --> H[HTML/CSS/JS Response]
    F --> I[Backend Code Execution]
    G --> J[Database Query/Response]

    %% Color Definitions
    class E webServer;
    class F appServer;
    class G dbServer;
    class H response;
    class I backendCode;
    class J databaseQuery;

    classDef webServer fill:#4CAF50,stroke:#333,stroke-width:2px;
    classDef appServer fill:#FFEB3B,stroke:#333,stroke-width:2px;
    classDef dbServer fill:#2196F3,stroke:#333,stroke-width:2px;
    classDef response fill:#FFC107,stroke:#333,stroke-width:2px;
    classDef backendCode fill:#8BC34A,stroke:#333,stroke-width:2px;
    classDef databaseQuery fill:#FF5722,stroke:#333,stroke-width:2px;