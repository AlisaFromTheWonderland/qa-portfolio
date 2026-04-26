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
| TC01 | Valid request with payment_method `"Card"` | ```{ "user_name": "Pokemon", "payment_method": "Card", "age": 2, "credit": true }``` | ✅ `200 OK` | ```{ "user_id": "generated_id", "user_name": "Pokemon", "payment_method": "Card", "age": 2, "credit": true }``` |
| TC02 | Age > 100 | ```{ "user_name": "Jerry", "payment_method": "Bank", "age": 102, "credit": false }``` | ❌ `400 Bad Request` | ```{ "error": "age must be between 1 and 100" }``` |
| TC03 | Invalid `user_name` type | ```{ "user_name": 123, "payment_method": "Cash", "age": 30, "credit": false }``` | ❌ `400 Bad Request` | ```{ "error": "user_name must be string" }``` |
| TC04 | Invalid `payment_method` | ```{ "user_name": "Pikachu", "payment_method": "ApplePay", "age": 20, "credit": true }``` | ❌ `400 Bad Request` | ```{ "error": "Invalid payment_method" }``` |
| TC05 | Valid request with payment_method `"Cash"` | ```{ "user_name": "BabyShark", "payment_method": "Cash", "age": 3, "credit": true }``` | ✅ `200 OK` | ```{ "user_id": "generated_id", "user_name": "BabyShark", "payment_method": "Cash", "age": 3, "credit": true }``` |
| TC06 | Invalid `credit` type | ```{ "user_name": "KitKat", "payment_method": "Bank", "age": 25, "credit": "no" }``` | ❌ `400 Bad Request` | ```{ "error": "credit must be boolean" }``` |
| TC07 | Age < 1 | ```{ "user_name": "Bober", "payment_method": "Card", "age": 0, "credit": true }``` | ❌ `400 Bad Request` | ```{ "error": "age must be between 1 and 100" }``` |
