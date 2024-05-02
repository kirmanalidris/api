# App License management API Reference
Management license for your wordpress theme or plugin /php/javascript

Update your WordPress themes and plugins easily and safely 

# Add new lincese
### HTTP Request

`POST https://kirmanalidris.com/app/license/api/add_license`

> To authorize, use this code:

```php

```

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

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
  "user_domain": "[]",
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

---


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


```

---
