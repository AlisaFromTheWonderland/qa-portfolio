# API Test Cases — `POST /Create_User`

## API Method Description

### Preconditions:
Method: POST
Endpoint: Create_User
Content-Type: application/json
Request: { user_name (req) str, payment_method (req) str possible values [Card|Bank|Cash], age int [1-100], credit boolean }
Response: { user_id str, user_name, payment_method, age, credit }

| ID | Name | Data | Status Code | Response |
|---|---|---|---|---|
| TC01 | Valid request with payment_method `"Card"` | ```{ "user_name": "Pokemon", "payment_method": "Card", "age": 2, "credit": true }``` | ✅ `200 OK` | ```json\n{ "user_id": "generated_id", "user_name": "Pokemon", "payment_method": "Card", "age": 2, "credit": true }\n``` |
| TC02 | Age > 100 | ```json\n{ "user_name": "Jerry", "payment_method": "Bank", "age": 102, "credit": false }\n``` | ❌ `400 Bad Request` | ```json\n{ "error": "age must be between 1 and 100" }\n``` |
| TC03 | Invalid `user_name` type | ```json\n{ "user_name": 123, "payment_method": "Cash", "age": 30, "credit": false }\n``` | ❌ `400 Bad Request` | ```json\n{ "error": "user_name must be string" }\n``` |
| TC04 | Invalid `payment_method` | ```json\n{ "user_name": "Pikachu", "payment_method": "ApplePay", "age": 20, "credit": true }\n``` | ❌ `400 Bad Request` | ```json\n{ "error": "Invalid payment_method" }\n``` |
| TC05 | Valid request with payment_method `"Cash"` | ```json\n{ "user_name": "BabyShark", "payment_method": "Cash", "age": 3, "credit": true }\n``` | ✅ `200 OK` | ```json\n{ "user_id": "generated_id", "user_name": "BabyShark", "payment_method": "Cash", "age": 3, "credit": true }\n``` |
| TC06 | Invalid `credit` type | ```json\n{ "user_name": "KitKat", "payment_method": "Bank", "age": 25, "credit": "no" }\n``` | ❌ `400 Bad Request` | ```json\n{ "error": "credit must be boolean" }\n``` |
| TC07 | Age < 1 | ```json\n{ "user_name": "Bober", "payment_method": "Card", "age": 0, "credit": true }\n``` | ❌ `400 Bad Request` | ```json\n{ "error": "age must be between 1 and 100" }\n``` |
