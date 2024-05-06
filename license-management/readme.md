# Official library for integration with third party applications 
Use this code library to make integration easier in your application or use the API base reference for more

[PHP application ](https://github.com/kirmanalidris/api/tree/dev/license-management/php)

[Javascript application ](https://github.com/kirmanalidris/api/tree/dev/license-management/javascript)

----------------------------

# API Reference
Management license for your wordpress theme or plugin /php/javascript

Update your WordPress themes and plugins easily and safely 

> All request body type is ```application/x-www-form-urlencoded```

# Add new lincese
### HTTP Request

`POST https://kirmanalidris.com/app/license/api/add_license`
parameter | default | description
----------|---------|------------
client_id | null | ```license client_id``` required.
product_id | null | ```license product_id``` required.
purchase_key | null | required.
max_domain | null | required.
is_unlimited | null | required.
has_expiry | null | required.
expiry_time | null | required.
has_support | null | required.
support_end_time | null | required.
status | null | ```active``` ```waiting``` ```inactive``` ```refunded``` required.
```php
$url = 'https://kirmanalidris.com/app/license/api/add_license';
$data = array(
  'admin_id'=> '543785342873436',
  'product_id'=> '1',
  'client_id'=> '1',
  'purchase_key'=> 'purchase_key',
  'max_domain'=> '2',
  'status'=> 'active',
   );

$ch = curl_init($url);
curl_setopt($ch, CURLOPT_POST, 1);
curl_setopt($ch, CURLOPT_POSTFIELDS, $data);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);

$response = curl_exec($ch);
curl_close($ch);

// Proses respons di sini
echo json_encode($response);
```
### response 
```json
{
  "status": 1,
  "message": "license added",
  "response": {
    "license_id": 13 //current insert license id
  }
}
```

-----------------------------------

# View lincese
### HTTP Request

`POST https://kirmanalidris.com/app/license/api/view_license`

> Displays license data based on license code 

Parameter | Default | Description
--------- | ------- | -----------
license_key | false | user license to check.
admin_id | null | apikey or admin_id obtained from kirmanalidris.com. (required).
```php

```

## response data
```json
{
  "response": 1,
  "message": "license ok",
  "admin_id": "543785342873436",
  "id": "1",
  "client_id": "1",
  "product_id": "1",
  "product_base_name": "plugin-custom-update",
  "license_id": "1",
  "purchase_key": "OdnA5VezyKJonCxTlqFd",
  "user_domain": "[\"app.kirmanalidris.com\",\"test.kirmanalidris.com\"]",
  "server_ip": "",
  "current_version": "",
  "using_version": "",
  "license_title": "",
  "max_domain": "2",
  "is_unlimited": "no",
  "verification_required": "",
  "has_expiry": "no",
  "expiry_time": "2024-04-21 15:30:00",
  "has_support": "unlimited",
  "support_end_time": "2024-04-21 15:30:00",
  "entry_time": "2024-05-05 12:19:07",
  "active_time": "2024-05-05 12:19:07",
  "request_counter": "5",
  "request_delay_time": "60",
  "status": "active"
}
```


-------------------------------------------------

# Validate lincese
### HTTP Request

`POST https://kirmanalidris.com/app/license/api/validate_license`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
license_key | false | user license for activate.
product_base_name | null | script folder name.
admin_id | null | apikey or admin_id obtained from kirmanalidris.com. (required).
domain | [] | user domain to be activated user domain to be activated (optional).
action | null | required ```activte``` ```deactivate```.


```php
$url = 'https://kirmanalidris.com/app/license/api/validate_license';
$data = array(
    'license_key' => 'user_license_key',
    'product_base_name' => 'name-folder-of-script',
    'admin_id' => 1234567890, // admin ID obtained from kirmanalidris.com
    'domain' => 'app.kirmanalidris.id'
    'action' => 'activate', // activate or deactivate
);

$ch = curl_init($url);
curl_setopt($ch, CURLOPT_POST, 1);
curl_setopt($ch, CURLOPT_POSTFIELDS, $data);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);

$response = curl_exec($ch);
curl_close($ch);

// Proses respons di sini
echo json_encode($response);

```

## response success 
```json
{
  "response": 1,
  "message": "license ok",
  "admin_id": "54378534428734365",
  "id": "1",
  "client_id": "1",
  "product_id": "1",
  "product_base_name": "plugin-custom-update",
  "license_id": "1",
  "purchase_key": "4t2i34L10AQaWV8hVTFeK",
  "user_domain": "['domain.com','domain.net','domain.id']",
  "server_ip": "",
  "current_version": "",
  "using_version": "",
  "license_title": "",
  "max_domain": "10",
  "is_unlimited": "no",
  "verification_required": "",
  "has_expiry": "no",
  "expiry_time": "2024-04-21 15:30:00",
  "has_support": "yes",
  "support_end_time": "2025-04-21 15:30:00",
  "entry_time": "2024-05-01 17:58:24",
  "active_time": "2024-05-01 17:58:24",
  "request_counter": "5",
  "request_delay_time": "60",
  "status": "active"
}

```

----------------------------------------


# list product
### HTTP Request

`POST https://kirmanalidris.com/app/license/api/list_product`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
admin_id | null | apikey or admin_id obtained from kirmanalidris.com. (required).


```php
$url = 'https://kirmanalidris.com/app/license/api/list_product';
$data = array(
    'admin_id' => 1234567890, // admin ID obtained from kirmanalidris.com
    );

$ch = curl_init($url);
curl_setopt($ch, CURLOPT_POST, 1);
curl_setopt($ch, CURLOPT_POSTFIELDS, $data);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);

$response = curl_exec($ch);
curl_close($ch);

// Proses respons di sini
echo json_encode($response);

```

## response

```json
[
  {
    "admin_id": "543785342873436",
    "id": "1",
    "name": "Plugin custom update",
    "product_base_name": "plugin-custom-update",
    "type": "plugin",
    "product_url": null,
    "is_premium": "yes"
  },
  {
    "admin_id": "543785342873436",
    "id": "2",
    "name": "theme custom update",
    "product_base_name": "theme-custom-update",
    "type": "theme",
    "product_url": null,
    "is_premium": "yes"
  },
  {
    "admin_id": "543785342873436",
    "id": "3",
    "name": "lp6",
    "product_base_name": "lp6-kirmanalidris",
    "type": "theme",
    "product_url": null,
    "is_premium": "yes"
  },
  {
    "admin_id": "543785342873436",
    "id": "4",
    "name": "wpwalogin",
    "product_base_name": "wpwalogin-kirmanalidris",
    "type": "plugin",
    "product_url": null,
    "is_premium": "yes"
  }
]
```

---------------------------------------------------

## Client add 
```POST http://kirmanalidris.com/app/license/api/add_client```

parameter | default | description
----------|---------|--------------
admin_id | null | required. 
client_name | null | required.
email | null | required.
phone | null | required.

### response
```json
{
  "status": "1",
  "message": "client added0",
  "response": {
    "client_id": 10 //current insert id
  }
}
```


### response failed
```json
{
  "status": "0",
  "message": "Email exist"
}
```



