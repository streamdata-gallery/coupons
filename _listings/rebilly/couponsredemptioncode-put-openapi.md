---
swagger: "2.0"
x-collection-name: Rebilly
x-complete: 0
info:
  title: Rebilly Create or update a coupon with predefined redemption code
  description: Create or update a coupon with predefined redemption code
  termsOfService: https://www.rebilly.com/terms/
  contact:
    name: Rebilly API Support
    url: https://www.rebilly.com/contact/
    email: integrations@rebilly.com
  version: "2.1"
host: api.rebilly.com
basePath: /v2.1
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /coupons:
    get:
      summary: Retrieve a list of coupons
      description: Retrieve a list of coupons
      operationId: coupons.get
      x-api-path-slug: coupons-get
      parameters:
      - in: query
        name: No Name
      responses:
        1:
          description: Photoset not found - The photoset id passed was not the id
            of avalid photoset owned by the calling user
        2:
          description: Photo not found - The photo id passed was not the id of a valid
            photo owned by the calling user
        95:
          description: SSL is required - SSL is required to access the Flickr API
        96:
          description: Invalid signature - The passed signature was invalid
        97:
          description: Missing signature - The call required signing but no signature
            was sent
        98:
          description: Login failed / Invalid auth token - The login details or auth
            token passed were invalid
        99:
          description: User not logged in / Insufficient permissions - The method
            requires user authentication but the user was not logged in, or the authenticated
            method call did not have the required permissions
        100:
          description: Invalid API Key - The API key passed was not valid or has expired
        105:
          description: Service currently unavailable - The requested service is temporarily
            unavailable
        106:
          description: Write operation failed - The requested operation failed due
            to a temporary issue
        111:
          description: Format "xxx" not found - The requested response format was
            not found
        112:
          description: Method "xxx" not found - The requested method was not found
        114:
          description: Invalid SOAP envelope - The SOAP envelope send in the request
            could not be parsed
        115:
          description: Invalid XML-RPC Method Call - The XML-RPC request document
            could not be parsed
        116:
          description: Bad URL found - One or more arguments contained a URL that
            has been used for abuse on Flickr
        200:
          description: OK
      tags:
      - Retrieve
      - List
      - Of
      - Coupons
    post:
      summary: Create a coupon
      description: Create a coupon
      operationId: coupons.post
      x-api-path-slug: coupons-post
      parameters:
      - in: body
        name: body
        description: Coupon resource
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Coupon
  /coupons/{redemptionCode}/expiration:
    post:
      summary: Set a coupon's expiration time.
      description: |-
        Set a coupon's expiry time with the specified redemption code.
        The expiredTime of a coupon must be greater than its issuedTime.
        This cannot be performed on expired coupons.
      operationId: coupons.redemptionCode.expiration.post
      x-api-path-slug: couponsredemptioncodeexpiration-post
      parameters:
      - in: body
        name: body
        description: Coupon resource
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Set
      - Coupons
      - Expiration
      - Time
  /coupons-redemptions:
    get:
      summary: Retrieve a list of coupon redemptions
      description: ""
      operationId: coupons_redemptions.get
      x-api-path-slug: couponsredemptions-get
      parameters:
      - in: query
        name: No Name
      responses:
        200:
          description: OK
      tags:
      - Retrieve
      - List
      - Of
      - Coupon
      - Redemptions
    post:
      summary: Redeem a coupon
      description: Redeem a coupon
      operationId: coupons_redemptions.post
      x-api-path-slug: couponsredemptions-post
      parameters:
      - in: body
        name: body
        description: Redeem a coupon
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Redeem
      - Coupon
  /coupons-redemptions/{id}:
    get:
      summary: Retrieve a coupon redemption with specified identifier string
      description: ""
      operationId: coupons_redemptions.id.get
      x-api-path-slug: couponsredemptionsid-get
      responses:
        200:
          description: OK
      tags:
      - Retrieve
      - Coupon
      - Redemption
      - Specified
      - Identifier
      - String
  /coupons-redemptions/{id}/cancel:
    post:
      summary: Cancel a coupon redemption
      description: ""
      operationId: coupons_redemptions.id.cancel.post
      x-api-path-slug: couponsredemptionsidcancel-post
      responses:
        200:
          description: OK
      tags:
      - Cancel
      - Coupon
      - Redemption
  /coupons/{redemptionCode}:
    get:
      summary: Retrieve a coupon
      description: Retrieve a coupon with specified redemption code string
      operationId: coupons.redemptionCode.get
      x-api-path-slug: couponsredemptioncode-get
      responses:
        200:
          description: OK
      tags:
      - Retrieve
      - Coupon
    put:
      summary: Create or update a coupon with predefined redemption code
      description: Create or update a coupon with predefined redemption code
      operationId: coupons.redemptionCode.put
      x-api-path-slug: couponsredemptioncode-put
      parameters:
      - in: body
        name: body
        description: Coupon resource
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Update
      - Coupon
      - Predefined
      - Redemption
      - Code
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---