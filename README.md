# holbertonschool-Fix_My_Code_Challenge




flowchart TB
    subgraph FE[Frontend - HTML/CSS/JavaScript]
        UI[Interface Utilisateur]
        PWGen[Générateur Mot de passe]
        ClientCrypto[Cryptographie Client]
    end

    subgraph BE[Backend - Python/Flask]
        API[API Flask]
        Auth[Service Auth]
        PWManager[Gestionnaire MDP]
        PWEncryption[Password Encryption]
    end

    subgraph DB[Base de données]
        MySQL[(MySQL)]
    end

    %% Frontend flows
    UI --> ClientCrypto
    UI --> PWGen
    ClientCrypto --> API

    %% Backend flows
    API --> Auth
    API --> PWManager
    Auth --> PWEncryption
    PWManager --> PWEncryption
    
    %% Database flows
    PWEncryption --> MySQL

    %% Styling with darker text
    classDef frontend fill:#f0f4f8,stroke:#1a365d,color:#000000,font-weight:bold
    classDef backend fill:#f0fdf4,stroke:#114e23,color:#000000,font-weight:bold
    classDef database fill:#fdf2f8,stroke:#721c47,color:#000000,font-weight:bold

    class UI,PWGen,ClientCrypto frontend
    class API,Auth,PWManager,PWEncryption backend
    class MySQL database 