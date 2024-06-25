## ahoService/UpdateStaffForItem

### Description:
Метод `UpdateStaffForItem` предназначен для присваивания или удаления устройства или предмета для сотрудника.

### Message:
```
{
    "item_id": "2-47169",
    "staff_id": "1-21"
}
```

|Name|Type||Description|
|-|-|-|--|
|item_id|string|Обязательное поле|ID устройства или предмета|
|staff_id|string|Обязательное поле|ID сотрудника|

### Response:

Code 0

OK

Example Value:

```
{
    "retro_map": [
        {
            "type": "RETRO_TYPE_1M",
            "date": {
                "seconds": "1693483200",
                "nanos": 0
            }
        }
    ],
    "id": "2-47161",
    "staff_id": "1-266",
    "attestation_date": null,
    "meet": {
        "date": null,
        "status": false
    }
}
```
### Response:

CODE 13 INTERNAL

Operation couldn’t be completed because of an internal error at the server.    

Error: internal error
