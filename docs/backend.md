# Backend
## 必要なAPI
### /login
いったん放置

### /table/equipment
| Kind     | Description                                          |
| -------- | ---------------------------------------------------- |
| URI      | /api/v1/get/equipment/infomation                     | 
| Method   | Get                                                  |
| headers  | {'Content-Type': 'application/json', 'token': token} |
| Response | JSON(以下に示す)                                     |
- 成功時
```json=
{
    "status": 200,
    "data": {
        "equip_1": string,
        "equip_2": string,
        "equip_3": string,
        "equip_name": string,
        "equip_man_num": string,
        "rental_status": string, 
        "remarks": string,
    }
}
```
- APIリクエスト失敗時
```json=
{
    "status": 400,
    "msg": string,
}
```
- サーバエラー時
```json=
{
    "status": 500,
    "msg": string,
}
```

### /table/equipment/my 
| Kind     | Description                                          |
| -------- | ---------------------------------------------------- |
| URI      | /api/v1/get/equipment/infomation?user_id=[int]       | 
| Method   | Get                                                  |
| headers  | {'Content-Type': 'application/json', 'token': token} |
| Response | JSON(以下に示す)                                     |
- 成功時
```json=
{
    "status": 200,
    "data": {
        "total_num": int,
        "equip_kind": string,
        "equip_num": string,
        "equip_man_num": string,
        "rental_period": [
            "year": int,
            "month": int,
            "day": int,
        ],
        "remarks": string
    }
}
```
- APIリクエスト失敗時
```json=
{
    "status": 400,
    "msg": string,
}
```
- サーバエラー時
```json=
{
    "status": 500,
    "msg": string,
}
```

### /request/lending
| Kind    | Description                                          |
| ------- | ---------------------------------------------------- |
| URI     | /api/v1/register/lending                                  | 
| Method  | POST                                                 |
| headers | {'Content-Type': 'application/json', 'token': token} |
| body    | JSON(以下に示す)                                     |
- 成功時
```json=
{
    "status": 201,
    "data": {
        "equip_1": string,
        "equip_2": string,
        "equip_3": string,
        "begin_year": int,
        "begin_month": int,
        "begin_day": int,
        "end_year": int,
        "end_month": int,
        "end_day": int,
        "overview": string,
        "detail": string
    }
}
```
- APIリクエスト失敗時
```json=
{
    "status": 400,
    "msg": string,
}
```
- サーバエラー時
```json=
{
    "status": 500,
    "msg": string,
}
```

### /request/return
#### 返却物取得(ID)
| Kind     | Description                                          |
| -------- | ---------------------------------------------------- |
| URI      | /api/v1/get/equipment/id?user_id=[user_id]           | 
| Method   | GET                                                  |
| headers  | {'Content-Type': 'application/json', 'token': token} |
| Response | JSON(以下に示す)                                     |
- 成功時
```json=
{
    "status": 200,
    "data": {
        "equipment": [ 
            string:int,
            ...
            string:int,
        ]
    }
}
```
```
※ data.equipmentの中は返却物の名前:idが取得できる。
```
- APIリクエスト失敗時
```json=
{
    "status": 400,
    "msg": string,
}
```
- サーバエラー時
```json=
{
    "status": 500,
    "msg": string,
}
```
#### 返却申請
| Kind    | Description                                          |
| ------- | ---------------------------------------------------- |
| URI     | /api/v1/register/return                              | 
| Method  | POST                                                 |
| headers | {'Content-Type': 'application/json', 'token': token} |
| Body    | JSON(以下に示す)                                     |
- 成功時
```json=
{
    "status": 201,
    "data": {
        "return_id": int,
        "remakrs": string,
    }
}
```
- APIリクエスト失敗時
```json=
{
    "status": 400,
    "msg": string,
}
```
- サーバエラー時
```json=
{
    "status": 500,
    "msg": string,
}
```

### /admin/equipment/register
| Kind    | Description                                          |
| ------- | ---------------------------------------------------- |
| URI     | /api/v1/register/equipment                           |
| Method  | POST                                                 |
| headers | {'Content-Type': 'application/json', 'token': token} |
| Body    | JSON(以下に示す)                                     |
- 成功時
```json=
{
    "status": 201,
    "data": {
        "equip_1": string,
        "equip_2": string,
        "equip_3": string,
        "equip_name": string,
        "equip_man_num", string,
        "possible_lental": string,
        "remarks": string,
    }
}
```
- APIリクエスト失敗時
```json=
{
    "status": 400,
    "msg": string,
}
```
- サーバエラー時
```json=
{
    "status": 500,
    "msg": string,
}
```
### /admin/equipment/deletion
| Kind    | Description                                          |
| ------- | ---------------------------------------------------- |
| URI     | /api/v1/delete/equipment                             |
| Method  | DELETE                                               |
| headers | {'Content-Type': 'application/json', 'token': token} |
| Body    | JSON(以下に示す)                                     |
- 成功時
```json=
{
    "status": 201,
    "data": {
        "equip_man_num": string,
    }
}
```
- APIリクエスト失敗時
```json=
{
    "status": 400,
    "msg": string,
}
```
- サーバエラー時
```json=
{
    "status": 500,
    "msg": string,
}
```

### /admin/equipment/change/[item_id]
| Kind    | Description                                          |
| ------- | ---------------------------------------------------- |
| URI     | /api/v1/change/equipment                             | 
| Method  | PUT                                                  |
| headers | {'Content-Type': 'application/json', 'token': token} |
| Body    | JSON(以下に示す)                                     |
- 成功時
```json=
{
    "status": 201,
    "data": {
        "equip_man_num": string,
        "change_item": string,
        "change_detail": string,
    }
}
```
- APIリクエスト失敗時
```json=
{
    "status": 400,
    "msg": string,
}
```
- サーバエラー時
```json=
{
    "status": 500,
    "msg": string,
}
```

### /admin/user/register
| Kind    | Description                                          |
| ------- | ---------------------------------------------------- |
| URI     | /api/v1/register/user                                |
| Method  | POST                                                 |
| headers | {'Content-Type': 'application/json', 'token': token} |
| Body    | JSON(以下に示す)                                     |
- 成功時
```json=
{
    "status": 201,
    "data": {
        "name": string,
        "student_num": int,
        "password": string,
    }
}
```
- APIリクエスト失敗時
```json=
{
    "status": 400,
    "msg": string,
}
```
- サーバエラー時
```json=
{
    "status": 500,
    "msg": string,
}
```

### /admin/user/deletion
| Kind    | Description                                          |
| ------- | ---------------------------------------------------- |
| URI     | /api/v1/delete/user                                  |
| Method  | DELETE                                               |
| headers | {'Content-Type': 'application/json', 'token': token} |
| Body    | JSON(以下に示す)                                     | 
- 成功時
```json=
{
    "status": 201,
    "data": {
        "name": string,
        "student_num": int,
        "password": string,
    }
}
```
- APIリクエスト失敗時
```json=
{
    "status": 400,
    "msg": string,
}
```
- サーバエラー時
```json=
{
    "status": 500,
    "msg": string,
}
```

### /admin/user/change/[user_id]
| Kind    | Description                                          |
| ------- | ---------------------------------------------------- |
| URI     | /api/v1/change/user                                  | 
| Method  | PUT                                                  |
| headers | {'Content-Type': 'application/json', 'token': token} |
| Body    | JSON(以下に示す)                                     |
- 成功時
```json=
{
    "status": 201,
    "data": {
        "change_item": string,
        "change_detail": string,
        "password": string,
    }
}
```
- APIリクエスト失敗時
```json=
{
    "status": 400,
    "msg": string,
}
```
- サーバエラー時
```json=
{
    "status": 500,
    "msg": string,
}
```

### /admin/equipment/aproval/[id] 
| Kind    | Description                                          |
| ------- | ---------------------------------------------------- |
| URI     | /api/v1/register/aproval/equipment                   |
| Method  | POST                                                 |
| headers | {'Content-Type': 'application/json', 'token': token} |
| Body    | JSON(以下に示す)                                     |
- 成功時
```json=
{
    "status": 201,
    "data": {
        "detail": string,
        "allow": string,
    }
}
```
- APIリクエスト失敗時
```json=
{
    "status": 400,
    "msg": string,
}
```
- サーバエラー時
```json=
{
    "status": 500,
    "msg": string,
}
```