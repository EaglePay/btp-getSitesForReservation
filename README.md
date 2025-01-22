### API Specification: `getSitesForReservation`

#### **Purpose**
This API fetches comprehensive details of sites available for reservation, including their amenities, pricing, hours, pictures, ratings, and reviews.

---

### **Base URL**
`https://api.parknation.org`

---

### **Endpoint**
- **URL**: `/email/getSitesForReservation`
- **Method**: `POST`
- **Description**: Retrieves detailed information about sites for reservations, including site-specific data like pictures, amenities, pricing, ratings, reviews, and operating hours.

---

### **Headers**
The following headers are required for the API call:
- `accept`: `application/json`
- `content-type`: `application/json`

---

### **Request**

#### **Body**
- **Type**: `JSON`
- **Example**:
  ```json
  {
    "site_id": -1
  }
  ```
- **Parameters**:
  | Parameter | Type    | Required | Description                                    |
  |-----------|---------|----------|------------------------------------------------|
  | `site_id` | Integer | Yes      | ID of the site to filter reservations. Use `-1` to fetch all sites. |

---

### **Response**

#### **Success Response**
- **HTTP Status Code**: `200 OK`
- **Type**: `application/json`
- **Structure**:
  ```json
  {
    "message": "getSitesForReservation Sent",
    "messageType": "success",
    "sites": [...],
    "sitePics": [...],
    "siteReviews": [...],
    "siteHours": [...]
  }
  ```

---

### **Key Sections in Response**

#### **1. Sites**
Detailed information for each site.
- **Example**:
  ```json
   {
      "created_at": "2024-10-05T11:58:28.793Z",
      "updated_at": "2025-01-15T22:42:42.247Z",
      "created_by": "****",
      "updated_by": "****",
      "site_id": 140,
      "name": " *****",
      "description": " 150 Parking Spaces, Lighted, Hard Packed or Paved, Restrooms, Security Cameras. 1.5 miles to fuel, fast food, convenience stores.",
      "status": true,
      "city": "Princeton",
      "state": "NJ",
      "zipcode": "*****",
      "comment": " ",
      "contact_info": "SD",
      "address_line_1": "******",
      "address_line_2": " ",
      "country": "US",
      "tax_rate": 34,
      "deleted_at": null,
      "logo_url": "*****",
      "web_site_url": "",
      "theme": "1",
      "logo_company_name": "HTP1",
      "site_phone_number": "*******",
      "site_email": "test@st.com",
      "is_affiliate": "Y",
      "longitude": "-74.7024",
      "latitude": "40.3297",
      "imagesURL": "*****",
      "site_type": "P",
      "site_logo_base64": "",
      "site_twilio_number": "",
      "site_time_zone": "EST",
      "site_locale": "en",
      "has_lumper_service": "N",
      "has_security_guard": "N",
      "has_lights": "N",
      "has_fence": "N",
      "has_cameras": "Y",
      "has_lpr": "N",
      "has_restrooms": "Y",
      "has_gate": "N",
      "has_repair_shop": "N",
      "has_cross_dock": "N",
      "has_office_space": "N",
      "has_24_7_access": "N",
      "has_limited_entry_exit_times": "N",
      "has_roaming_security": "N",
      "has_snow_removal": "N",
      "has_truck_wash": "N",
      "has_uber_lyft_taxi": "N",
      "has_food_restaurant_in_area": "N",
      "has_paid_container_stacking_services": "N",
      "has_reapirs_allowed_no_fluids": "N",
      "has_double_stacked_bobtails_allowed": "N",
      "has_monthly_assigned_spaces_available": "N",
      "has_oversize_allowed": "N",
      "has_hazmat_allowed": "N",
      "has_automated_gate": "N",
      "has_security_at_gate": "N",
      "has_plaid_access": "Y",
      "vacancyCount": 3,
      "site_live_camera_id": null,
      "site_daily_rate": 25,
      "site_weekly_rate": 100,
      "site_monthly_rate": 200,
      "site_convenience_fee": 3,
      "custom_name": "Delaware1",
      "has_siteowner_consent": "Y",
      "selectedAmenities": [
          "Cameras",
          "Restrooms"
      ],
      "key": "****",
      "searchText": "*****"
  }
  ```
  
| Field                 | Type       | Description                                    |
|-----------------------|------------|------------------------------------------------|
| `site_id`             | Integer    | Unique identifier for the site.               |
| `name`                | String     | Name of the site.                             |
| `description`         | String     | Detailed description of the site.             |
| `created_at`          | DateTime   | The timestamp when the site was created.      |
| `updated_at`          | DateTime   | The timestamp when the site was last updated. |
| `created_by`          | Integer    | ID of the user who created the site.          |
| `updated_by`          | Integer    | ID of the user who last updated the site.     |
| `status`              | Boolean    | Indicates if the site is active.              |
| `city`, `state`, `zipcode` | String | Address details.                              |
| `contact_info`        | String     | Contact information for the site.             |
| `address_line_1`      | String     | Primary address line.                         |
| `address_line_2`      | String     | Secondary address line.                       |
| `country`             | String     | Country where the site is located.            |
| `latitude`            | String     | Latitude of the site.                         |
| `longitude`           | String     | Longitude of the site.                        |
| `site_daily_rate`     | Decimal    | Daily parking rate.                           |
| `site_weekly_rate`    | Decimal    | Weekly parking rate.                          |
| `site_monthly_rate`   | Decimal    | Monthly parking rate.                         |
| `tax_rate`            | Decimal    | Tax rate applied to the site.                 |
| `vacancyCount`        | Integer    | Available parking spots.                      |
| `selectedAmenities`   | Array      | List of available amenities at the site.      |
| `logo_url`            | String     | URL for the site's logo.                      |
| `has_lights`          | String     | Indicates if the site has lighting.           |
| `has_cameras`         | String     | Indicates if the site has cameras.            |
| `has_restrooms`       | String     | Indicates if the site has restrooms.          |
| `custom_name`         | String     | Custom name for the site.                     |

---

#### **2. Site Pictures**
List of pictures associated with each site.
- **Example**:
  ```json
  {
    "site_pic_id": 29,
    "site_id_fk": 5,
    "name": "New",
    "description": "1",
    "status": 1,
    "image_url": "https://example.com/image.png"
  }
  ```

| Field       | Type    | Description                                    |
|-------------|---------|------------------------------------------------|
| `site_pic_id` | Integer | Unique identifier for the picture.            |
| `site_id_fk`  | Integer | ID of the associated site.                    |
| `name`       | String  | Picture name or title.                        |
| `image_url`  | String  | URL of the picture.                           |

---

#### **3. Site Hours**
Operating hours for each site.
- **Example**:
  ```json
  {
    "site_id": 10,
    "site_name": "Atco",
    "weekday": "Monday",
    "business_open": "09:00",
    "business_close": "17:00",
    "lot_open": "00:00",
    "lot_close": "23:59",
    "business_closed": false
  }
  ```

| Field              | Type    | Description                                |
|--------------------|---------|--------------------------------------------|
| `weekday`          | String  | Day of the week.                          |
| `business_open`    | String  | Business opening time (24-hour format).   |
| `business_close`   | String  | Business closing time (24-hour format).   |
| `lot_open`         | String  | Parking lot opening time (24-hour format).|
| `lot_close`        | String  | Parking lot closing time (24-hour format).|

---

#### **4. Site Reviews**
Customer reviews and ratings for each site.
- **Example**:
  ```json
  {
    "site_review_id": 13,
    "site_id_fk": 5,
    "rating": 5,
    "review_text": "Great place!",
    "AverageRating": 4.5,
    "TotalReviews": 12
  }
  ```

| Field             | Type    | Description                                 |
|-------------------|---------|---------------------------------------------|
| `rating`          | Integer | Rating given by a customer (1-5).           |
| `review_text`     | String  | Review text.                                |
| `AverageRating`   | Decimal | Average rating for the site.                |
| `TotalReviews`    | Integer | Total number of reviews for the site.       |

---

### **Error Response**
- **HTTP Status Code**: `400 Bad Request`
- **Type**: `application/json`
- **Example**:
  ```json
  {
    "message": "Invalid site_id provided",
    "messageType": "error"
  }
  ```

---

### **Error Handling**
| Status Code | Message                           | Cause                         |
|-------------|-----------------------------------|-------------------------------|
| `400`       | `Invalid site_id provided`       | Incorrect or missing `site_id`. |
| `500`       | `Internal Server Error`          | Server encountered an issue.  |

---

