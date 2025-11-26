# Realty In Us MCP Server

[English](./README_EN.md) | [简体中文](./README.md) | 繁體中文

## 🚀 使用 EMCP 平台快速體驗

**[EMCP](https://sit-emcp.kaleido.guru)** 是一個強大的 MCP 伺服器管理平台，讓您無需手動配置即可快速使用各種 MCP 伺服器！

### 快速開始：

1. 🌐 造訪 **[EMCP 平台](https://sit-emcp.kaleido.guru)**
2. 📝 註冊並登入帳號
3. 🎯 進入 **MCP 廣場**，瀏覽所有可用的 MCP 伺服器
4. 🔍 搜尋或找到本伺服器（`bach-realty_in_us`）
5. 🎉 點擊 **「安裝 MCP」** 按鈕
6. ✅ 完成！即可在您的應用中使用

### EMCP 平台優勢：

- ✨ **零配置**：無需手動編輯配置檔案
- 🎨 **視覺化管理**：圖形介面輕鬆管理所有 MCP 伺服器
- 🔐 **安全可靠**：統一管理 API 金鑰和認證資訊
- 🚀 **一鍵安裝**：MCP 廣場提供豐富的伺服器選擇
- 📊 **使用統計**：即時查看服務調用情況

立即造訪 **[EMCP 平台](https://sit-emcp.kaleido.guru)** 開始您的 MCP 之旅！


---

## 簡介

這是一個使用 [FastMCP](https://fastmcp.wiki) 自動生成的 MCP 伺服器，用於存取 Realty In Us API。

- **PyPI 套件名**: `bach-realty_in_us`
- **版本**: 1.0.0
- **傳輸協定**: stdio


## 安装

### 从 PyPI 安装:

```bash
pip install bach-realty_in_us
```

### 从源码安装:

```bash
pip install -e .
```

## 运行

### 方式 1: 使用 uvx（推荐，无需安装）

```bash
# 运行（uvx 会自动安装并运行）
uvx --from bach-realty_in_us bach_realty_in_us

# 或指定版本
uvx --from bach-realty_in_us@latest bach_realty_in_us
```

### 方式 2: 直接运行（开发模式）

```bash
python server.py
```

### 方式 3: 安装后作为命令运行

```bash
# 安装
pip install bach-realty_in_us

# 运行（命令名使用下划线）
bach_realty_in_us
```

## 配置

### API 認證

此 API 需要認證。請設定環境變數:

```bash
export API_KEY="your_api_key_here"
```

### 環境變數

| 變數名 | 說明 | 必需 |
|--------|------|------|
| `API_KEY` | API 金鑰 | 是 |




### 在 Claude Desktop 中使用

编辑 Claude Desktop 配置文件 `claude_desktop_config.json`:


```json
{
  "mcpServers": {
    "realty_in_us": {
      "command": "python",
      "args": ["E:\path\to\realty_in_us\server.py"],
      "env": {
        "API_KEY": "your_api_key_here"
      }
    }
  }
}
```

**注意**: 請將 `E:\path\to\realty_in_us\server.py` 替換為實際的伺服器檔案路徑。


## 可用工具

此服务器提供以下工具:


### `propertiesv3list`

List properties for sale, rent, sold with options and filters

**端点**: `POST /properties/v3/list`



---


### `agentsv2search_location`

Search location information

**端点**: `GET /agents/v2/search-location`


**参数**:

- `area_types` (string): One of the followings : neighborhood|city|county|postal_code|building|street

- `limit` (string): For paging purpose (max 20)

- `input` (string) *必需*: Any term or phrase that you are familiar with. Ex : California



---


### `agentsget_listings_deprecated`

Get agent's listings

**端点**: `GET /agents/get-listings`


**参数**:

- `fulfillment_id` (string) *必需*: The value of advertiser_id field returned in .../agents/list endpoint

- `id` (string) *必需*: The value of abbreviation field returned in .../agents/list endpoint

- `agent_id` (string) *必需*: The value of ...member/id JSON object returned in .../agents/list endpoint

- `type` (string): One of the following : all|forSale|forSold|forRent|openHouses

- `page` (string): For paging purpose



---


### `agentsget_recommendations_deprecated`

Get agent's recommendations

**端点**: `GET /agents/get-recommendations`


**参数**:

- `advertiser_id` (string) *必需*: The value of advertiser_id field returned in .../agents/list endpoint



---


### `agentsget_profile_deprecated`

Get agent profile

**端点**: `GET /agents/get-profile`


**参数**:

- `advertiser_id` (string) *必需*: The value of advertiser_id field returned in .../agents/list endpoint

- `nrds_id` (string) *必需*: The value of nrds_id field returned in .../agents/list endpoint



---


### `agentslist_deprecated`

List agents with filters and options

**端点**: `GET /agents/list`


**参数**:

- `postal_code` (string) *必需*: Zip code or postal code

- `offset` (string): The offset of items to be ignored in response for paging

- `limit` (string): For paging purpose (max 20)

- `sort` (string): One of the followings : recent_activity_high|recently_sold_high|for_sale_count_high|recommendations_count_high|agent_rating_high

- `name` (string): Search for agent or team or company by name

- `types` (string): One of the followings : agent | team | office

- `agent_type` (string): One of the followings or leave empty : buyer | seller

- `recommendations_count_min` (string): Number of recommendations (max 10)

- `agent_rating_min` (string): Rating (max 5)

- `price_min` (string): Option filter by setting min price

- `price_max` (string): Option filter by setting max price



---


### `agentsv2get_listings`

Get agent listings

**端点**: `GET /agents/v2/get-listings`


**参数**:

- `fulfillment_id` (string) *必需*: The value of fulfillment_id field returned in .../agents/v2/list endpoint



---


### `agentsv2get_recommendations`

Get agent recommendations

**端点**: `GET /agents/v2/get-recommendations`


**参数**:

- `fulfillment_id` (string) *必需*: The value of fulfillment_id field returned in .../agents/v2/list endpoint



---


### `agentsv2get_reviews`

Get agent reviews

**端点**: `GET /agents/v2/get-reviews`


**参数**:

- `fulfillment_id` (string) *必需*: The value of fulfillment_id field returned in .../agents/v2/list endpoint



---


### `agentsv2get_profile`

Get agent profile

**端点**: `GET /agents/v2/get-profile`


**参数**:

- `profile_id` (string) *必需*: The value of id field returned in .../agents/v2/list endpoint

- `fulfillment_id` (string): The value of fulfillment_id field returned in .../agents/v2/list endpoint



---


### `agentsv2list`

List agents with filters and options

**端点**: `GET /agents/v2/list`


**参数**:

- `postal_code` (string) *必需*: Zip code or postal code. Either marketing_area_city, name, postal_code is required

- `offset` (string): The offset of items to be ignored in response for paging

- `limit` (string): For paging purpose (max 20)

- `sort` (string): One of the followings : RATINGS_REVIEWS|RELEVANT_AGENTS|MOST_SALES|TESTIMONIALS_RECOMMENDATIONS|MOST_RECENT_ACTIVITY

- `name` (string): Search for agent or team or company by name. Either marketing_area_city, name, postal_code is required

- `agent_type` (string): One of the followings or leave empty : BUYER|SELLER

- `agent_filter_criteria` (string): One of the followings : NRDS_AND_FULFILLMENT_ID_EXISTS|NRDS_ID_EXISTS|FULFILLMENT_ID_EXISTS

- `marketing_area_city` (string): The value of id returned in .../agents/v2/search-location endpoint. Ex : md_california Either marketing_area_city, name, postal_code is required

- `languages` (string): One of the followings : spanish|chinese|french|amharic|arabic|aramaic|portuguese|hindi|russian|afrikaans|albanian|asl|armenian|bengali|bosnian|bulgarian|croatian|czech|danish|dutch|english|estonian|farsi|filipino|finnish|gaelic|georgian|german|greek|gujarati|hawaiian|hebrew|hmong|hungarian|indonesian|italian|japanese|khmer|korean|lao|latvian|lithuanian|malay|malayalam|mandarin|nepali|norwegian|pashto|polish|punjabi|romanian|serbian|sindhi|singhalese|slovenian|somali|swahili|swedish|tagalog|taiwa



---


### `financerates`

Get finance rates

**端点**: `GET /finance/rates`


**参数**:

- `loc` (string) *必需*: The postal code



---


### `mortgagecheck_equity_rates_deprecated`

Check mortgage equity rates

**端点**: `GET /mortgage/check-equity-rates`


**参数**:

- `creditScore` (string) *必需*: One of the following : excellent|good|fair|poor

- `loanProduct` (string) *必需*: One of the following : HELOC,HELOAN_FIXED_5YEARS,HELOAN_FIXED_10YEARS,HELOAN_FIXED_15YEARS,HELOAN_FIXED_20YEARS,HELOAN_FIXED_30YEARS. Separate by comma for multiple applied values

- `loanAmount` (string) *必需*: Example value: 70000

- `propertyValue` (string) *必需*: Example value: 300000

- `mortgageBalance` (string) *必需*: Example value: 150000

- `zip` (string) *必需*: The postal code

- `state` (string) *必需*: The state code



---


### `mortgagecalculate_deprecated`

Calculate mortgage

**端点**: `GET /mortgage/calculate`


**参数**:

- `hoi` (string) *必需*: Home insurance

- `tax_rate` (string) *必需*: Property tax

- `downpayment` (string) *必需*: Down payment

- `price` (string) *必需*: Home price

- `term` (string) *必需*: Mortgage loan type

- `rate` (string) *必需*: Interest rate



---


### `mortgagecheck_rates_deprecated`

Check mortgage rates

**端点**: `GET /mortgage/check-rates`


**参数**:

- `creditScore` (string) *必需*: One of the following : excellent|good|fair|poor

- `points` (string) *必需*: One of the following : all|zero|zero_to_one|one_to_two

- `loanPurpose` (string) *必需*: purchase|refinance

- `loanTypes` (string) *必需*: One of the following : ALL|30YrFixed|30YrFixed_FHA|30YrFixed_VA|20YrFixed|15YrFixed|10YrFixed|5Arm|7Arm

- `loanPercent` (string) *必需*: Example value: 85.2

- `propertyPrice` (string) *必需*: Example value: 250000

- `zip` (string) *必需*: The postal code



---


### `mortgagev2check_rates`

Check mortgage rates

**端点**: `GET /mortgage/v2/check-rates`


**参数**:

- `postal_code` (string) *必需*: The postal code



---


### `mortgagecalculate_affordability_deprecated`

Calculate affordability

**端点**: `GET /mortgage/calculate-affordability`


**参数**:

- `annual_income` (string) *必需*: Example value: 250000

- `debt_to_income_ratio` (string) *必需*: Example value: 0.43

- `down_payment` (string) *必需*: Example value: 172000

- `hoa_fees` (string): Example value: 0

- `homeowner_insurance_rate` (string) *必需*: Example value: 0.012

- `interest_rate` (string) *必需*: Example value: 0.03119

- `is_pmi_included` (string): Example value: 

- `loan_term` (string) *必需*: Example value: 30

- `monthly_debt` (string) *必需*: Example value: 1500

- `tax_rate` (string) *必需*: Example value: 0.01



---


### `propertiesv2list_for_sale_deprecated`

List properties for sale

**端点**: `GET /properties/v2/list-for-sale`


**参数**:

- `city` (string) *必需*: The value of city field responded in locations/auto-complete API (do not use this parameter with postal_code)

- `state_code` (string) *必需*: The value of state_code field responded in locations/auto-complete API (do not use this parameter with postal_code)

- `postal_code` (string): Zip code or postal code (do not use this parameter with city and state_code)

- `offset` (string) *必需*: The offset of items to be ignored in response for paging

- `limit` (string) *必需*: The number of items to be responded in every request

- `sort` (string): One of the followings (separated by comma for multiple values): relevance|newest|price_low|price_high|photos|open_house_date|sqft_high|price_reduced_date

- `prop_type` (string): One of the followings (separated by comma for multiple values): single_family,multi_family,condo,mobile,land,farm,other

- `prop_sub_type` (string): One of the followings (separated by comma for multiple values): condo,cond_op,townhouse,co_op

- `features` (string): One of the followings (separated by comma for multiple values): garage_2_or_more,view,waterfront,golf_course_view,swimming_pool,cul_de_sac,hardwood_floors,basement,fireplace,energy_efficient,disability_features,dining_room,washer_dryer,family_room,den_or_office,game_room,central_air,central_heat,forced_air,single_story,two_or_more_stories,corner_lot,water_view,golf_course_lot_or_frontage,hill_or_mountain_view,ocean_view,city_view,lake_view,river_view,community_security_features,community_swimmin

- `radius` (string): Radius in miles to look for properties (1 to 20)

- `age_min` (string): Min age of properties

- `age_max` (string): Max age of properties

- `sqft_min` (string): Min size of the properties

- `sqft_max` (string): Max size of the properties

- `baths_min` (string): Min baths of properties

- `beds_min` (string): Min beds of properties

- `price_min` (string): Option filter by setting min price

- `price_max` (string): Option filter by setting max price

- `lot_sqft_min` (string): Min Lot/Acreage size

- `lot_sqft_max` (string): Max Lot/Acreage size

- `is_matterports` (string): Example value: 

- `is_foreclosure` (string): Example value: 

- `has_open_house` (string): Example value: 

- `is_new_construction` (string): Example value: 

- `is_contingent` (string): Example value: 

- `is_pending` (string): Example value: 

- `is_new_plan` (string): Example value: 

- `lat_max` (string): Look for properties in bounding box, this is the max latitude of the coordinate. Has no affect if postal_code, or city or state_code parameter has value.

- `lat_min` (string): Look for properties in bounding box, this is the min latitude of the coordinate. Has no affect if postal_code, or city or state_code parameter has value.

- `lng_max` (string): Look for properties in bounding box, this is the max longitude of the coordinate. Has no affect if postal_code, or city or state_code parameter has value.

- `lng_min` (string): Look for properties in bounding box, this is the min longitude of the coordinate. Has no affect if postal_code, or city or state_code parameter has value.



---


### `propertiesv2list_by_mls_deprecated`

List properties by MLS ID

**端点**: `GET /properties/v2/list-by-mls`


**参数**:

- `mls_id` (string) *必需*: The MLS ID

- `prop_status` (string): One of the followings : for_sale|for_rent|recently_sold

- `offset` (string): The offset of items to be ignored in response for paging

- `limit` (string): The number of items per response



---


### `propertiesv2detail_deprecated`

Get property detail information

**端点**: `GET /properties/v2/detail`


**参数**:

- `property_id` (string) *必需*: The value of property_id field returned in .../properties/list-.... or .../properties/v2/list-... endpoints.



---


### `propertieslist_for_rent_deprecated`

List properties for rent

**端点**: `GET /properties/list-for-rent`


**参数**:

- `state_code` (string) *必需*: The value of state_code field responded in locations/auto-complete API (do not use this parameter with postal_code)

- `city` (string) *必需*: The value of city field responded in locations/auto-complete API (do not use this parameter with postal_code)

- `postal_code` (string): Zip code or postal code (do not use this parameter with city and state_code)

- `limit` (string) *必需*: The number of items to be responded in every request

- `offset` (string) *必需*: The offset of items to be ignored in response for paging

- `sort` (string): One of the followings : completeness,photos,freshest|price_low|price_high|photos|newest

- `radius` (string): Radius in miles to look for properties

- `baths_min` (string): Option filter by setting at least the number of bathrooms

- `beds_min` (string): Option filter by setting at least the number of bedrooms

- `price_min` (string): Option filter by setting min price

- `price_max` (string): Option filter by setting max price

- `sqft_min` (string): Min size of the properties

- `sqft_max` (string): Max size of the properties

- `prop_type` (string): One of the followings (separated by comma for multiple values): apartment,single_family,mapi_condo_townhome,other

- `mapi_community_features` (string): One of the followings (separated by comma for multiple values): community_washer_dryer,community_parking,central_air,community_pool,community_gym

- `listed_date_min` (string): Date string format yyyy-MM-dd'T'HH:mm:ss'Z' , such as : 2019-08-01T16:24:40Z .The date from which the properties have been on realtor.com

- `allows_dogs` (string): Example value: 

- `allows_cats` (string): Example value: 

- `no_pets_allowed` (string): Example value: 

- `lat_max` (string): Look for properties in bounding box, this is the max latitude of the coordinate. Has no affect if postal_code, or city or state_code parameter has value.

- `lat_min` (string): Look for properties in bounding box, this is the min latitude of the coordinate. Has no affect if postal_code, or city or state_code parameter has value.

- `lng_max` (string): Look for properties in bounding box, this is the max longitude of the coordinate. Has no affect if postal_code, or city or state_code parameter has value.

- `lng_min` (string): Look for properties in bounding box, this is the min longitude of the coordinate. Has no affect if postal_code, or city or state_code parameter has value.



---


### `propertiesv2list_for_rent_deprecated`

List properties for rent

**端点**: `GET /properties/v2/list-for-rent`


**参数**:

- `city` (string) *必需*: The value of city field responded in locations/auto-complete API (do not use this parameter with postal_code)

- `state_code` (string) *必需*: The value of state_code field responded in locations/auto-complete API (do not use this parameter with postal_code)

- `postal_code` (string): Zip code or postal code (do not use this parameter with city and state_code)

- `limit` (string) *必需*: The number of items to be responded in every request

- `offset` (string) *必需*: The offset of items to be ignored in response for paging

- `sort` (string): One of the followings : relevance|newest|price_low|price_high|photos|open_house_date|sqft_high|price_reduced_date

- `prop_type` (string): One of the followings (separated by comma for multiple values): single_family,multi_family,condo,mobile,land,farm,other

- `prop_sub_type` (string): One of the followings (separated by comma for multiple values): condo,cond_op,townhouse,co_op

- `features` (string): One of the followings (separated by comma for multiple values): recreation_facilities,swimming_pool,washer_dryer,garage_1_or_more,central_air,fireplace,spa_or_hot_tub,dishwasher,community_doorman,community_elevator,furnished,laundry_room,community_no_fee,community_outdoor_space,pets_allowed

- `radius` (string): Radius in miles to look for properties (1 to 20)

- `beds_min` (string): Min beds of properties

- `baths_min` (string): Min baths of properties

- `price_min` (string): Option filter by setting min price

- `price_max` (string): Option filter by setting max price

- `lot_sqft_min` (string): Min Lot/Acreage size

- `lot_sqft_max` (string): Max Lot/Acreage size

- `sqft_min` (string): Min size of the properties

- `sqft_max` (string): Max size of the properties

- `allows_dogs` (string): Example value: 

- `allows_cats` (string): Example value: 

- `lat_max` (string): Look for properties in bounding box, this is the max latitude of the coordinate. Has no affect if postal_code, or city or state_code parameter has value.

- `lat_min` (string): Look for properties in bounding box, this is the min latitude of the coordinate. Has no affect if postal_code, or city or state_code parameter has value.

- `lng_max` (string): Look for properties in bounding box, this is the max longitude of the coordinate. Has no affect if postal_code, or city or state_code parameter has value.

- `lng_min` (string): Look for properties in bounding box, this is the min longitude of the coordinate. Has no affect if postal_code, or city or state_code parameter has value.



---


### `locationsauto_complete_deprecated`

Get auto complete suggestions by city, ward, street name to pass in other endpoints. This endpoint also helps to get a specific property id by its address

**端点**: `GET /locations/auto-complete`


**参数**:

- `input` (string) *必需*: Name of cities, districts, places



---


### `propertieslist_sold_deprecated`

List sold properties

**端点**: `GET /properties/list-sold`


**参数**:

- `city` (string) *必需*: The value of city field responded in locations/auto-complete API (do not use this parameter with postal_code)

- `state_code` (string) *必需*: The value of state_code field responded in locations/auto-complete API (do not use this parameter with postal_code)

- `postal_code` (string): Zip code or postal code (do not use this parameter with city and state_code)

- `offset` (string) *必需*: The offset of items to be ignored in response for paging

- `limit` (string) *必需*: The number of items to be responded in every request

- `sort` (string): One of the followings : price_low|price_high

- `prop_type` (string): One of the followings (separated by comma for multiple values): single_family, condo, mobile, multi_family, farm, land

- `radius` (string): Radius in miles to look for properties

- `age_min` (string): Min age of home

- `age_max` (string): Max age of home

- `sqft_min` (string): Min size of the properties

- `sqft_max` (string): Max size of the properties

- `lot_sqft_min` (string): Min Lot/Acreage size

- `lot_sqft_max` (string): Max Lot/Acreage size

- `price_min` (string): Option filter by setting min price

- `price_max` (string): Option filter by setting max price

- `lat_max` (string): Look for properties in bounding box, this is the max latitude of the coordinate. Has no affect if postal_code, or city or state_code parameter has value.

- `lat_min` (string): Look for properties in bounding box, this is the min latitude of the coordinate. Has no affect if postal_code, or city or state_code parameter has value.

- `lng_max` (string): Look for properties in bounding box, this is the max longitude of the coordinate. Has no affect if postal_code, or city or state_code parameter has value.

- `lng_min` (string): Look for properties in bounding box, this is the min longitude of the coordinate. Has no affect if postal_code, or city or state_code parameter has value.



---


### `locationsv2auto_complete`

Get auto complete suggestions by city, ward, street name to pass in other endpoints. This endpoint also helps to get a specific property id by its address

**端点**: `GET /locations/v2/auto-complete`


**参数**:

- `input` (string) *必需*: States, cities, districts, addresses, zipcode. Ex : California Los Angeles 2425 Sahalee Dr W Sammamish, WA

- `limit` (string): The number of items per response, for paging purpose



---


### `mortgagev2calculate`

Calculate mortgage

**端点**: `GET /mortgage/v2/calculate`


**参数**:

- `home_insurance` (string) *必需*: Home insurance

- `property_tax_rate` (string) *必需*: Property tax

- `down_payment` (string) *必需*: Down payment

- `price` (string) *必需*: Home price

- `term` (string) *必需*: Mortgage loan type

- `rate` (string) *必需*: Interest rate

- `hoa_fees` (string) *必需*: Home owner association fee

- `apply_veterans_benefits` (string): Example value: 



---


### `schoolsdetail`

Get detailed information of a school

**端点**: `GET /schools/detail`


**参数**:

- `id` (string) *必需*: The value of schools -> id field returned in .../schools/list endpoint



---


### `schoolslist`

List schools with options and filters

**端点**: `GET /schools/list`


**参数**:

- `limit` (string): The number of items per response, for paging purpose

- `offset` (string): The offset of records to ignore, for paging purpose

- `state_code` (string) *必需*: Filter schools by state (You need to specify at least one of the following : state_code|city|county|neighborhood|postal_code|school_district_id)

- `city` (string): Filter schools by city (You need to specify at least one of the following : state_code|city|county|neighborhood|postal_code|school_district_id)

- `county` (string): Filter schools by county (You need to specify at least one of the following : state_code|city|county|neighborhood|postal_code|school_district_id)

- `neighborhood` (string): Filter schools by neighborhood (You need to specify at least one of the following : state_code|city|county|neighborhood|postal_code|school_district_id)

- `postal_code` (string): Filter schools by postal_code (You need to specify at least one of the following : state_code|city|county|neighborhood|postal_code|school_district_id)

- `school_district_id` (string): Filter schools by school_district_id (You need to specify at least one of the following : state_code|city|county|neighborhood|postal_code|school_district_id)

- `education_level` (string): One of the following : elementary|high|middle|private



---


### `schoolsget_school_district`

Get detailed information of a school district

**端点**: `GET /schools/get-school-district`


**参数**:

- `id` (string) *必需*: The value of districts -> id field returned in .../schools/list endpoint



---


### `propertieslist_for_sale_deprecated`

List properties for sale

**端点**: `GET /properties/list-for-sale`


**参数**:

- `state_code` (string) *必需*: The value of state_code field responded in locations/auto-complete API (do not use this parameter with postal_code)

- `city` (string) *必需*: The value of city field responded in locations/auto-complete API (do not use this parameter with postal_code)

- `postal_code` (string): Zip code or postal code (do not use this parameter with city and state_code)

- `offset` (string) *必需*: The offset of items to be ignored in response for paging

- `limit` (string) *必需*: The number of items to be responded in every request

- `sort` (string): One of the followings (relevance | price_low | price_high | photos | newest | open_house_date | sqft_high | price_reduced_date)

- `radius` (string): Radius in miles to look for properties

- `prop_type` (string): One of the followings (separated by comma for multiple values): single_family,condo,mobile,multi_family,farm,land

- `listed_date_min` (string): Date string format yyyy-MM-dd'T'HH:mm:ss'Z' , such as : 2019-08-01T16:24:40Z .The date from which the properties have been on realtor.com

- `baths_min` (string): Option filter by setting at least the number of bathrooms

- `beds_min` (string): Option filter by setting at least the number of bedrooms

- `reduced` (string): true/false - Price reduced only

- `price_min` (string): Option filter by setting min price

- `price_max` (string): Option filter by setting max price

- `features` (string): One of the followings (separated by comma for multiple values): basement,den_or_office,dining_room,family_room,game_room,washer_dryer,energy_efficient_home,central_air,central_heat,forced_air,carport,garage_1_or_more,garage_2_or_more,garage_3_or_more,rv_or_boat_parking,disability_features,fireplace,hardwood_floors,horse_facilities,spa_or_hot_tub,swimming_pool,tennis_court,single_story,two_or_more_stories,lease_option,pets_allowed,corner_lot,cul_de_sac,golf_course_lot_or_frontage,waterfront,city_

- `age_min` (string): Min age of home

- `age_max` (string): Max age of home

- `lot_sqft_min` (string): Min Lot/Acreage size

- `lot_sqft_max` (string): Max Lot/Acreage size

- `sqft_min` (string): Min size of the properties

- `sqft_max` (string): Max size of the properties

- `is_foreclosure` (string): Example value: 

- `is_matterports` (string): Example value: 

- `is_new_construction` (string): Example value: 

- `is_pending` (string): Example value: 

- `is_contingent` (string): Example value: 

- `lat_max` (string): Look for properties in bounding box, this is the max latitude of the coordinate. Has no affect if postal_code, or city or state_code parameter has value.

- `lat_min` (string): Look for properties in bounding box, this is the min latitude of the coordinate. Has no affect if postal_code, or city or state_code parameter has value.

- `lng_max` (string): Look for properties in bounding box, this is the max longitude of the coordinate. Has no affect if postal_code, or city or state_code parameter has value.

- `lng_min` (string): Look for properties in bounding box, this is the min longitude of the coordinate. Has no affect if postal_code, or city or state_code parameter has value.



---


### `propertiesv3detail`

Get property detail information (include new Home Value feature)

**端点**: `GET /properties/v3/detail`


**参数**:

- `listing_id` (string): The value of listing_id field returned in .../properties/.../list endpoint

- `property_id` (string) *必需*: The value of property_id field returned in .../properties/.../list endpoint



---


### `propertiesv3get_surroundings`

Get surroundings data around  a property

**端点**: `GET /properties/v3/get-surroundings`


**参数**:

- `property_id` (string) *必需*: The value of property_id field returned in .../properties/.../list endpoint

- `enable_flood` (string): Example value: 



---


### `propertiesv3list_similar_homes`

List similar homes

**端点**: `GET /properties/v3/list-similar-homes`


**参数**:

- `property_id` (string) *必需*: The value of property_id field returned in .../properties/.../list endpoint

- `limit` (string): The number of items per response, for paging purpose

- `status` (string): One of the following : for_sale|ready_to_build|for_rent|sold|off_market|other|new_community



---


### `propertiesv2list_similar_homes_deprecated`

List similar properties for sale * This endpoint is deprecating, the official have changed to use .../properties/v2/list.... endpoints to list similar properties.

**端点**: `GET /properties/v2/list-similar-homes`


**参数**:

- `property_id` (string) *必需*: The value of property_id field returned in .../properties/list-.... or .../properties/v2/list-... endpoints.



---


### `propertiesv3get_photos`

Get photos of a property

**端点**: `GET /properties/v3/get-photos`


**参数**:

- `property_id` (string) *必需*: The value of property_id field returned in .../properties/.../list endpoint



---


### `propertiesdetail_deprecated`

Get property detail information

**端点**: `GET /properties/detail`


**参数**:

- `listing_id` (string) *必需*: The value of listing_id field returned in .../properties/list-.... or .../properties/v2/list-... endpoints.

- `prop_status` (string) *必需*: One of the followings : for_sale|for_rent

- `property_id` (string) *必需*: The value of property_id field returned in .../properties/list-.... or .../properties/v2/list-... endpoints.



---


### `propertiesv3get_commute_time`

Get commute time to travel to a location

**端点**: `GET /properties/v3/get-commute-time`


**参数**:

- `destination_address` (string) *必需*: An address, you should use .../locations/v2/auto-complete to get a complete and correct address . Ex : 7830 Poppy Blvd

- `property_id` (string) *必需*: The value of property_id field returned in .../properties/.../list endpoint

- `transportation_type` (string): One of the following : bicycling|driving|transit|walking

- `with_traffic` (string): Example value: 



---


### `propertiesv2list_sold_deprecated`

List sold properties

**端点**: `GET /properties/v2/list-sold`


**参数**:

- `offset` (string) *必需*: The offset of items to be ignored in response for paging

- `limit` (string) *必需*: The number of items to be responded in every request

- `city` (string) *必需*: The value of city field responded in locations/auto-complete API (do not use this parameter with postal_code)

- `state_code` (string) *必需*: The value of state_code field responded in locations/auto-complete API (do not use this parameter with postal_code)

- `postal_code` (string): Zip code or postal code (do not use this parameter with city and state_code)

- `sort` (string): One of the followings : sold_date|beds_high|price_low|price_high|lot_sqft_high

- `prop_type` (string): One of the followings (separated by comma for multiple values): single_family,multi_family,condo,mobile,land,farm,other

- `radius` (string): Radius in miles to look for properties (1 to 20)

- `baths_min` (string): Min baths of properties

- `beds_min` (string): Min beds of properties

- `price_min` (string): Option filter by setting min price

- `price_max` (string): Option filter by setting max price

- `lot_sqft_min` (string): Min Lot/Acreage size

- `lot_sqft_max` (string): Max Lot/Acreage size

- `age_min` (string): Min age of home

- `age_max` (string): Max age of home

- `sqft_min` (string): Min size of the properties

- `sqft_max` (string): Max size of the properties

- `lat_max` (string): Look for properties in bounding box, this is the max latitude of the coordinate. Has no affect if postal_code, or city or state_code parameter has value.

- `lat_min` (string): Look for properties in bounding box, this is the min latitude of the coordinate. Has no affect if postal_code, or city or state_code parameter has value.

- `lng_max` (string): Look for properties in bounding box, this is the max longitude of the coordinate. Has no affect if postal_code, or city or state_code parameter has value.

- `lng_min` (string): Look for properties in bounding box, this is the min longitude of the coordinate. Has no affect if postal_code, or city or state_code parameter has value.



---


### `agentsget_reviews_deprecated`

Get agent reviews

**端点**: `GET /agents/get-reviews`


**参数**:

- `advertiser_id` (string) *必需*: The value of advertiser_id field returned in .../agents/list endpoint



---


### `schoolslist_nearby_deprecated`

List schools that are near the property

**端点**: `GET /schools/list-nearby`


**参数**:

- `lon` (string) *必需*: The longitude co-ordinate

- `lat` (string) *必需*: The latitude co-ordinate



---


### `propertiesv2list_similar_rental_homes_deprecated`

List similar properties for rent * This endpoint is deprecating, the official have changed to use .../properties/v2/list.... endpoints to list similar properties.

**端点**: `GET /properties/v2/list-similar-rental-homes`


**参数**:

- `postal_code` (string) *必需*: The value of postal_code field returned in all list endpoints

- `property_id` (string) *必需*: The value of property_id field returned in .../properties/list-.... or .../properties/v2/list-... endpoints.



---


### `propertieslist_similarities_deprecated`

List similar properties

**端点**: `GET /properties/list-similarities`


**参数**:

- `property_id` (string) *必需*: The value of property_id field returned in .../properties/list-.... or .../properties/v2/list-... endpoints.

- `limit` (string) *必需*: The number of items responded

- `prop_status` (string) *必需*: One of the followings : for_sale|for_rent



---


### `propertieslist_by_mls_deprecated`

List properties by MLS ID

**端点**: `GET /properties/list-by-mls`


**参数**:

- `mls_id` (string) *必需*: The MLS ID

- `limit` (string): The number of items per response

- `offset` (string): The offset of items to be ignored in response for paging

- `sort` (string): One of the followings : price_low|price_high|photos|newest|open_house_date



---



## 技术栈

- **FastMCP**: 快速、Pythonic 的 MCP 服务器框架
- **传输协议**: stdio
- **HTTP 客户端**: httpx

## 开发

此伺服器由 [API-to-MCP](https://github.com/BACH-AI-Tools/api-to-mcp) 工具自動生成。

版本: 1.0.0
