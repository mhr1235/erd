erDiagram
    EMPLOYEE {
        INTEGER employeeId PK
        TEXT name
        TEXT position
        TEXT hireDate
    }
    
    ADOPTER {
        INTEGER adopterId PK
        TEXT name
        TEXT phone
        TEXT email
    }
    
    PET {
        INTEGER petId PK
        TEXT name
        TEXT species
        TEXT breed
        TEXT arrivalDate
        INTEGER careEmployeeId FK
    }
    
    ADOPTION {
        INTEGER adoptionId PK
        INTEGER petId FK
        INTEGER adopterId FK
        INTEGER employeeId FK
        TEXT adoptionDate
    }

    %% Relationships
    EMPLOYEE ||--o{ PET : "cares for"
    EMPLOYEE ||--o{ ADOPTION : "handles paperwork for"
    ADOPTER ||--o{ ADOPTION : "makes"
    PET ||--o| ADOPTION : "is part of"
