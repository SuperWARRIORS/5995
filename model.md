```mermaid
flowchart LR
U[User] --> M[MainActivity<br/>Register]
M --> F[(credentials.txt)]
U --> L[Login]
L --> F
L --> S[(SharedPreferences<br>SessionPrefs/sessionToken)]
L --> P[Profile]
P --> S
```
