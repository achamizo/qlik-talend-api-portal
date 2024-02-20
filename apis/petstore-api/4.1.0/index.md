---
# NOTICE: Copyright 2024 Talend SA, Talend, Inc., and affiliates. All Rights Reserved. Customer’s use of the software contained herein is subject to the terms and conditions of the Agreement between Customer and Talend.
layout: "apiDefinition_1.1.0"
api-definition:
  specVersion: "4.1.0"
  info:
    name: "Petstore API"
    version: "4.1.0"
    description: "This is a sample server Petstore server.  You can find out more about Swagger at [http://swagger.io](http://swagger.io) or on [irc.freenode.net, #swagger](http://swagger.io/irc/).  For this sample, you can use the api key `special-key` to test the authorization filters."
    license:
      name: "Apache 2.0"
      url: "http://www.apache.org/licenses/LICENSE-2.0.html"
    contact:
      email: "apiteam@swagger.io"
    termsOfService: "http://swagger.io/terms/"
  contract:
    baseUrls:
    - url: "http://petstore.swagger.io/v2"
      isPublished: true
    mediaTypes:
    - "application/json"
    sections:
    - name: "Pet"
      elementOrder:
      - "#/contract/resources/8ab2c5e1-2489-4287-91f0-d6bb16122775"
      - "#/contract/resources/8b700dd4-ff77-4ad9-8b52-1e9f85837bf4"
      - "#/contract/resources/ab793302-e587-4da8-ad39-4dde2c839fa4"
      - "#/contract/resources/94ba6855-a205-4428-84e0-b01e445f210d"
      - "#/contract/resources/6bd63e8a-19a7-4e71-9f5c-d9e4b2c2de23"
      - "#/contract/types/3155fb64-434c-44ce-8b29-fa53c78ba12e"
      - "#/contract/types/ffabfe76-52ec-4bf9-96dd-d309fa424561"
      - "#/contract/types/50432841-7f7f-499c-a4c4-4cd3ea3cb01a"
      - "#/contract/types/5bf5f755-2477-408c-a794-9065af536092"
    - name: "Store"
      elementOrder:
      - "#/contract/resources/379abd1a-62ba-44bb-b3eb-396018376e5e"
      - "#/contract/resources/edc94099-2b30-4f5d-a264-692e47cbdc90"
      - "#/contract/resources/fc88083f-08d5-4ece-8692-62fe5a9dc5d8"
      - "#/contract/types/650a5fdd-49c1-4924-878e-a0d1bc9bbb5a"
    - name: "User"
      elementOrder:
      - "#/contract/resources/a72ef277-726d-4e02-bc8b-7f0917f2a1ff"
      - "#/contract/resources/ff205dd4-0666-44f2-8e18-6993a773dd49"
      - "#/contract/resources/c854ea37-37c5-43e2-aea5-c418b12042d3"
      - "#/contract/resources/72dd0d65-777e-45bc-b40e-af3adfc50082"
      - "#/contract/resources/e48966aa-d196-4d76-9c55-70e2e843e1d0"
      - "#/contract/resources/95646ed7-c569-4d73-9ad1-1f0de5eb1fdb"
      - "#/contract/types/0f294c7e-62fc-44e3-b2b5-820c1ffdbbdf"
    securitySchemes:
      "850cc28d-683f-4785-8177-17efe0d3239d":
        name: "petstore_auth"
        type: "oauth2"
        settings:
          authorizationUri: "http://petstore.swagger.io/oauth/dialog"
          authorizationGrants:
          - "implicit"
          scopes:
            "04826345-ef3e-431d-a12c-475e66c05b36":
              name: "write:pets"
              description: "modify pets in your account"
            d5585ca1-b882-4b48-b22a-84801f740994:
              name: "read:pets"
              description: "read your pets"
      "8503cf5e-ee44-47cd-b211-1e8eb3b77c6c":
        name: "api_key"
        type: "custom"
        describedBy:
          headers:
          - name: "api_key"
            type: "STRING"
    resources:
      ab793302-e587-4da8-ad39-4dde2c839fa4:
        path: "/pet"
        section: "#/contract/sections/b1e53699-68bd-40f8-813e-b50160a723b1"
        operations:
          be380936-7e09-4b4d-a34d-891357031ecc:
            name: "Update an existing pet"
            method: "PUT"
            description: ""
            operationId: "updatePet"
            tags:
            - "pet"
            securedBy:
            - scheme: "#/contract/securitySchemes/850cc28d-683f-4785-8177-17efe0d3239d"
              scopes:
              - "#/contract/securitySchemes/850cc28d-683f-4785-8177-17efe0d3239d/settings/scopes/04826345-ef3e-431d-a12c-475e66c05b36"
              - "#/contract/securitySchemes/850cc28d-683f-4785-8177-17efe0d3239d/settings/scopes/d5585ca1-b882-4b48-b22a-84801f740994"
            bodies:
            - type: "#/contract/types/3155fb64-434c-44ce-8b29-fa53c78ba12e"
              mediaTypes:
              - "application/json"
              - "application/xml"
            responses:
              d00d431d-53fa-4197-9f6d-674cd80cdc93:
                status: "400"
                description: "Invalid ID supplied"
              "57825f5c-35e5-4073-a6fa-1947d53a831e":
                status: "404"
                description: "Pet not found"
              e17c70dd-ff80-43da-a126-e95f933a8a73:
                status: "405"
                description: "Validation exception"
          "4567ac19-428f-4c96-87d8-58b879c8a961":
            name: "Add a new pet to the store"
            method: "POST"
            description: ""
            operationId: "addPet"
            tags:
            - "pet"
            securedBy:
            - scheme: "#/contract/securitySchemes/850cc28d-683f-4785-8177-17efe0d3239d"
              scopes:
              - "#/contract/securitySchemes/850cc28d-683f-4785-8177-17efe0d3239d/settings/scopes/04826345-ef3e-431d-a12c-475e66c05b36"
              - "#/contract/securitySchemes/850cc28d-683f-4785-8177-17efe0d3239d/settings/scopes/d5585ca1-b882-4b48-b22a-84801f740994"
            bodies:
            - type: "#/contract/types/3155fb64-434c-44ce-8b29-fa53c78ba12e"
              mediaTypes:
              - "application/json"
              - "application/xml"
            responses:
              "4da00d6c-4b9d-484d-84b3-0440498f2340":
                status: "405"
                description: "Invalid input"
      "8b700dd4-ff77-4ad9-8b52-1e9f85837bf4":
        path: "/pet/findByStatus"
        section: "#/contract/sections/b1e53699-68bd-40f8-813e-b50160a723b1"
        operations:
          "3da4ea0f-146c-494b-b452-e4d4a1b65700":
            name: "Finds Pets by status"
            method: "GET"
            description: "Multiple status values can be provided with comma separated strings"
            operationId: "findPetsByStatus"
            tags:
            - "pet"
            securedBy:
            - scheme: "#/contract/securitySchemes/850cc28d-683f-4785-8177-17efe0d3239d"
              scopes:
              - "#/contract/securitySchemes/850cc28d-683f-4785-8177-17efe0d3239d/settings/scopes/04826345-ef3e-431d-a12c-475e66c05b36"
              - "#/contract/securitySchemes/850cc28d-683f-4785-8177-17efe0d3239d/settings/scopes/d5585ca1-b882-4b48-b22a-84801f740994"
            queryParameters:
            - name: "status"
              type: "ARRAY"
              description: "Status values that need to be considered for filter"
              required: true
              items:
                type: "STRING"
                default: "available"
                enum:
                - "available"
                - "pending"
                - "sold"
            responses:
              "6654331c-e3e7-4212-aeb1-2e31967fd818":
                status: "200"
                description: "successful operation"
                bodies:
                - type: "ARRAY"
                  items:
                    type: "#/contract/types/3155fb64-434c-44ce-8b29-fa53c78ba12e"
                  mediaTypes:
                  - "application/xml"
                  - "application/json"
              "70574deb-3725-4ca0-9771-e0594a1cf0bd":
                status: "400"
                description: "Invalid status value"
      "8ab2c5e1-2489-4287-91f0-d6bb16122775":
        path: "/pet/findByTags"
        section: "#/contract/sections/b1e53699-68bd-40f8-813e-b50160a723b1"
        operations:
          afda4b22-b78a-46a4-abad-351e7f516610:
            name: "Finds Pets by tags"
            method: "GET"
            description: "Muliple tags can be provided with comma separated strings. Use tag1, tag2, tag3 for testing."
            operationId: "findPetsByTags"
            tags:
            - "pet"
            securedBy:
            - scheme: "#/contract/securitySchemes/850cc28d-683f-4785-8177-17efe0d3239d"
              scopes:
              - "#/contract/securitySchemes/850cc28d-683f-4785-8177-17efe0d3239d/settings/scopes/04826345-ef3e-431d-a12c-475e66c05b36"
              - "#/contract/securitySchemes/850cc28d-683f-4785-8177-17efe0d3239d/settings/scopes/d5585ca1-b882-4b48-b22a-84801f740994"
            queryParameters:
            - name: "tags"
              type: "ARRAY"
              description: "Tags to filter by"
              required: true
              items:
                type: "STRING"
            responses:
              "52479326-1436-4187-b8fd-576dd08f9514":
                status: "200"
                description: "successful operation"
                bodies:
                - type: "ARRAY"
                  items:
                    type: "#/contract/types/3155fb64-434c-44ce-8b29-fa53c78ba12e"
                  mediaTypes:
                  - "application/xml"
                  - "application/json"
              bc699891-9558-4952-bf6e-2d2c67b6d971:
                status: "400"
                description: "Invalid tag value"
      "94ba6855-a205-4428-84e0-b01e445f210d":
        path: "/pet/{petId}"
        section: "#/contract/sections/b1e53699-68bd-40f8-813e-b50160a723b1"
        pathVariables:
        - name: "petId"
          type: "INTEGER"
          description: "ID of pet to return"
          required: true
        operations:
          "8d94befd-ed55-4181-908b-e342b5231028":
            name: "Find pet by ID"
            method: "GET"
            description: "Returns a single pet"
            operationId: "getPetById"
            tags:
            - "pet"
            securedBy:
            - scheme: "#/contract/securitySchemes/8503cf5e-ee44-47cd-b211-1e8eb3b77c6c"
              scopes: []
            responses:
              "8d896a1e-6e59-4995-bfd9-5fc8d9cc533e":
                status: "200"
                description: "successful operation"
                bodies:
                - type: "#/contract/types/3155fb64-434c-44ce-8b29-fa53c78ba12e"
                  mediaTypes:
                  - "application/xml"
                  - "application/json"
              "4919a6f2-1ff8-493d-93e4-6d1be6a2f68d":
                status: "400"
                description: "Invalid ID supplied"
              c81268b7-f062-4431-a867-2297bdb6d554:
                status: "404"
                description: "Pet not found"
          "02c15703-a1a3-47a3-8420-708b6d99d12a":
            name: "Updates a pet in the store with form data"
            method: "POST"
            description: ""
            operationId: "updatePetWithForm"
            tags:
            - "pet"
            securedBy:
            - scheme: "#/contract/securitySchemes/850cc28d-683f-4785-8177-17efe0d3239d"
              scopes:
              - "#/contract/securitySchemes/850cc28d-683f-4785-8177-17efe0d3239d/settings/scopes/04826345-ef3e-431d-a12c-475e66c05b36"
              - "#/contract/securitySchemes/850cc28d-683f-4785-8177-17efe0d3239d/settings/scopes/d5585ca1-b882-4b48-b22a-84801f740994"
            bodies:
            - type: "OBJECT"
              properties:
              - name: "name"
                type: "STRING"
                description: "Updated name of the pet"
              - name: "status"
                type: "STRING"
                description: "Updated status of the pet"
              mediaTypes:
              - "application/x-www-form-urlencoded"
            responses:
              "352361f5-ffb0-45d7-a13e-f2d84d7f83fd":
                status: "405"
                description: "Invalid input"
          "1097797e-06e1-404d-b943-9468fb7cc100":
            name: "Deletes a pet"
            method: "DELETE"
            description: ""
            operationId: "deletePet"
            tags:
            - "pet"
            securedBy:
            - scheme: "#/contract/securitySchemes/850cc28d-683f-4785-8177-17efe0d3239d"
              scopes:
              - "#/contract/securitySchemes/850cc28d-683f-4785-8177-17efe0d3239d/settings/scopes/04826345-ef3e-431d-a12c-475e66c05b36"
              - "#/contract/securitySchemes/850cc28d-683f-4785-8177-17efe0d3239d/settings/scopes/d5585ca1-b882-4b48-b22a-84801f740994"
            headers:
            - name: "api_key"
              type: "STRING"
            responses:
              "32e8a492-7fcb-4050-b59b-024a186c90c8":
                status: "400"
                description: "Invalid ID supplied"
              "3c431c25-4416-4b10-8c60-603df39b6aee":
                status: "404"
                description: "Pet not found"
      "6bd63e8a-19a7-4e71-9f5c-d9e4b2c2de23":
        path: "/pet/{petId}/uploadImage"
        section: "#/contract/sections/b1e53699-68bd-40f8-813e-b50160a723b1"
        pathVariables:
        - name: "petId"
          type: "INTEGER"
          format: "INT64"
          description: "ID of pet to return"
          required: true
        operations:
          "8323c0a7-9874-4d3f-87b4-a05db886bf8b":
            name: "uploads an image"
            method: "POST"
            description: ""
            operationId: "uploadFile"
            tags:
            - "pet"
            securedBy:
            - scheme: "#/contract/securitySchemes/850cc28d-683f-4785-8177-17efe0d3239d"
              scopes:
              - "#/contract/securitySchemes/850cc28d-683f-4785-8177-17efe0d3239d/settings/scopes/04826345-ef3e-431d-a12c-475e66c05b36"
              - "#/contract/securitySchemes/850cc28d-683f-4785-8177-17efe0d3239d/settings/scopes/d5585ca1-b882-4b48-b22a-84801f740994"
            bodies:
            - type: "OBJECT"
              properties:
              - name: "additionalMetadata"
                type: "STRING"
                description: "Additional data to pass to server"
              - name: "file"
                type: "FILE"
                description: "file to upload"
              mediaTypes:
              - "multipart/form-data"
            responses:
              e93b8979-8b5a-4461-bb5e-b5430b97d485:
                status: "200"
                description: "successful operation"
                bodies:
                - type: "#/contract/types/5bf5f755-2477-408c-a794-9065af536092"
                  mediaTypes:
                  - "application/json"
      fc88083f-08d5-4ece-8692-62fe5a9dc5d8:
        path: "/store/inventory"
        section: "#/contract/sections/19c3ae49-ce34-4dd8-9556-7d653ebe5490"
        operations:
          db23ec47-776e-49a1-ac0d-2dc69d8b29aa:
            name: "Returns pet inventories by status"
            method: "GET"
            description: "Returns a map of status codes to quantities"
            operationId: "getInventory"
            tags:
            - "store"
            securedBy:
            - scheme: "#/contract/securitySchemes/8503cf5e-ee44-47cd-b211-1e8eb3b77c6c"
              scopes: []
            responses:
              "75851fa3-0386-45a3-b54c-c76e62c12f99":
                status: "200"
                description: "successful operation"
                bodies:
                - type: "OBJECT"
                  mediaTypes:
                  - "application/json"
      "379abd1a-62ba-44bb-b3eb-396018376e5e":
        path: "/store/order"
        section: "#/contract/sections/19c3ae49-ce34-4dd8-9556-7d653ebe5490"
        operations:
          "3816fac2-73c6-43f8-87e6-4c41270f5051":
            name: "Place an order for a pet"
            method: "POST"
            description: ""
            operationId: "placeOrder"
            tags:
            - "store"
            bodies:
            - type: "#/contract/types/650a5fdd-49c1-4924-878e-a0d1bc9bbb5a"
            responses:
              f0a3575e-165a-4ae1-91f7-f0ce28b7b146:
                status: "200"
                description: "successful operation"
                bodies:
                - type: "#/contract/types/650a5fdd-49c1-4924-878e-a0d1bc9bbb5a"
                  mediaTypes:
                  - "application/xml"
                  - "application/json"
              "2f28fa88-6c0b-40e5-96e8-a94b38a12a1e":
                status: "400"
                description: "Invalid Order"
      edc94099-2b30-4f5d-a264-692e47cbdc90:
        path: "/store/order/{orderId}"
        section: "#/contract/sections/19c3ae49-ce34-4dd8-9556-7d653ebe5490"
        pathVariables:
        - name: "orderId"
          type: "INTEGER"
          format: "INT64"
          required: true
          minimum: 1
          maximum: 10
        operations:
          "4e25864c-4acc-4e1a-93f2-e0442f913821":
            name: "Find purchase order by ID"
            method: "GET"
            description: "For valid response try integer IDs with value >= 1 and <= 10. Other values will generated exceptions"
            operationId: "getOrderById"
            tags:
            - "store"
            responses:
              "3141338e-bad4-40c3-b951-c1f4c303b07f":
                status: "200"
                description: "successful operation"
                bodies:
                - type: "#/contract/types/650a5fdd-49c1-4924-878e-a0d1bc9bbb5a"
                  mediaTypes:
                  - "application/xml"
                  - "application/json"
              "432d4cb0-064d-4725-a580-d245cd693277":
                status: "400"
                description: "Invalid ID supplied"
              "043b13a9-be14-4746-b2cc-e8ceba4e4a20":
                status: "404"
                description: "Order not found"
          c441e2e1-f24b-4412-8406-36bf165b4f05:
            name: "Delete purchase order by ID"
            method: "DELETE"
            description: "For valid response try integer IDs with positive integer value. Negative or non-integer values will generate API errors"
            operationId: "deleteOrder"
            tags:
            - "store"
            responses:
              "5938a9b0-800a-45b4-a0d1-99eb3bcecdb3":
                status: "400"
                description: "Invalid ID supplied"
              "1599d7ce-7e0e-4987-a6fa-f4dc6645c44b":
                status: "404"
                description: "Order not found"
      a72ef277-726d-4e02-bc8b-7f0917f2a1ff:
        path: "/user"
        section: "#/contract/sections/0144a1b3-15fe-41e4-af99-57889d0830c8"
        operations:
          "0150d33b-4014-46b9-b905-aca48cbbbdb9":
            name: "Create user"
            method: "POST"
            description: "This can only be done by the logged in user."
            operationId: "createUser"
            tags:
            - "user"
            bodies:
            - type: "#/contract/types/0f294c7e-62fc-44e3-b2b5-820c1ffdbbdf"
      ff205dd4-0666-44f2-8e18-6993a773dd49:
        path: "/user/createWithArray"
        section: "#/contract/sections/0144a1b3-15fe-41e4-af99-57889d0830c8"
        operations:
          a621bf7e-ee42-4357-b006-be47d4b6a396:
            name: "Creates list of users with given input array"
            method: "POST"
            description: ""
            operationId: "createUsersWithArrayInput"
            tags:
            - "user"
            bodies:
            - type: "ARRAY"
              items:
                type: "#/contract/types/0f294c7e-62fc-44e3-b2b5-820c1ffdbbdf"
      c854ea37-37c5-43e2-aea5-c418b12042d3:
        path: "/user/createWithList"
        section: "#/contract/sections/0144a1b3-15fe-41e4-af99-57889d0830c8"
        operations:
          c567a413-faac-4769-9b6f-a5997fd8bb22:
            name: "Creates list of users with given input array"
            method: "POST"
            description: ""
            operationId: "createUsersWithListInput"
            tags:
            - "user"
            bodies:
            - type: "ARRAY"
              items:
                type: "#/contract/types/0f294c7e-62fc-44e3-b2b5-820c1ffdbbdf"
      e48966aa-d196-4d76-9c55-70e2e843e1d0:
        path: "/user/login"
        section: "#/contract/sections/0144a1b3-15fe-41e4-af99-57889d0830c8"
        operations:
          "03417de3-da55-420b-a440-a46abd542c96":
            name: "Logs user into the system"
            method: "GET"
            description: ""
            operationId: "loginUser"
            tags:
            - "user"
            queryParameters:
            - name: "username"
              type: "STRING"
              description: "The user name for login"
              required: true
            - name: "password"
              type: "STRING"
              description: "The password for login in clear text"
              required: true
            responses:
              ca363a71-3323-4658-9c9e-b1b47a295a6a:
                status: "200"
                description: "successful operation"
                headers:
                - name: "X-Rate-Limit"
                  type: "INTEGER"
                  format: "INT32"
                  description: "calls per hour allowed by the user"
                - name: "X-Expires-After"
                  type: "DATETIME"
                  description: "date in UTC when token expires"
                bodies:
                - type: "STRING"
                  mediaTypes:
                  - "application/xml"
                  - "application/json"
              c3a144ba-2199-4f2e-9a46-ae1313683757:
                status: "400"
                description: "Invalid username/password supplied"
      "95646ed7-c569-4d73-9ad1-1f0de5eb1fdb":
        path: "/user/logout"
        section: "#/contract/sections/0144a1b3-15fe-41e4-af99-57889d0830c8"
        operations:
          bc470b15-5cdf-4b42-99d4-29ce9b506e72:
            name: "Logs out current logged in user session"
            method: "GET"
            operationId: "logoutUser"
            tags:
            - "user"
            responses:
              ac5f9ca7-8ccc-4275-b74a-ae3ce0469acf:
                status: "200"
      "72dd0d65-777e-45bc-b40e-af3adfc50082":
        path: "/user/{username}"
        section: "#/contract/sections/0144a1b3-15fe-41e4-af99-57889d0830c8"
        pathVariables:
        - name: "username"
          type: "STRING"
          description: "The name that needs to be fetched. Use user1 for testing."
          required: true
        operations:
          cabbe72f-cf47-45f2-afd1-df8f1091fe15:
            name: "Get user by user name"
            method: "GET"
            description: ""
            operationId: "getUserByName"
            tags:
            - "user"
            responses:
              "4f02c57e-4a40-4697-95dd-778d47fd0af3":
                status: "200"
                description: "successful operation"
                bodies:
                - type: "#/contract/types/0f294c7e-62fc-44e3-b2b5-820c1ffdbbdf"
                  mediaTypes:
                  - "application/xml"
                  - "application/json"
              "68473c65-9963-4807-bb6f-d5793000a1c1":
                status: "400"
                description: "Invalid username supplied"
              "3e2bcb3d-7f4a-4434-9462-7bafeb21f3e6":
                status: "404"
                description: "User not found"
          cb31b6f3-c885-42bd-b5a1-d97284acc110:
            name: "Updated user"
            method: "PUT"
            description: "This can only be done by the logged in user."
            operationId: "updateUser"
            tags:
            - "user"
            bodies:
            - type: "#/contract/types/0f294c7e-62fc-44e3-b2b5-820c1ffdbbdf"
            responses:
              "218ddafd-0111-4192-84d4-97bdc2e9cf2b":
                status: "400"
                description: "Invalid user supplied"
              c483e585-dd72-46be-bd5f-c62930892115:
                status: "404"
                description: "User not found"
          "2ab881fc-c147-43c7-840f-56dfa5ac4048":
            name: "Delete user"
            method: "DELETE"
            description: "This can only be done by the logged in user."
            operationId: "deleteUser"
            tags:
            - "user"
            responses:
              "2971064a-ef63-4f01-af2c-e64315367038":
                status: "400"
                description: "Invalid username supplied"
              ceeeba57-8cc2-46cb-b634-f0cf0c9628e4:
                status: "404"
                description: "User not found"
    types:
      "650a5fdd-49c1-4924-878e-a0d1bc9bbb5a":
        name: "Order"
        type: "OBJECT"
        section: "#/contract/sections/19c3ae49-ce34-4dd8-9556-7d653ebe5490"
        properties:
        - name: "id"
          type: "INTEGER"
          format: "INT64"
        - name: "petId"
          type: "INTEGER"
          format: "INT64"
        - name: "quantity"
          type: "INTEGER"
          format: "INT32"
        - name: "shipDate"
          type: "DATETIME"
        - name: "status"
          type: "STRING"
          description: "Order Status"
          enum:
          - "placed"
          - "approved"
          - "delivered"
        - name: "complete"
          type: "BOOLEAN"
          default: false
      "50432841-7f7f-499c-a4c4-4cd3ea3cb01a":
        name: "Category"
        type: "OBJECT"
        section: "#/contract/sections/b1e53699-68bd-40f8-813e-b50160a723b1"
        properties:
        - name: "id"
          type: "INTEGER"
          format: "INT64"
        - name: "name"
          type: "STRING"
      "0f294c7e-62fc-44e3-b2b5-820c1ffdbbdf":
        name: "User"
        type: "OBJECT"
        section: "#/contract/sections/0144a1b3-15fe-41e4-af99-57889d0830c8"
        properties:
        - name: "id"
          type: "INTEGER"
          format: "INT64"
        - name: "username"
          type: "STRING"
        - name: "firstName"
          type: "STRING"
        - name: "lastName"
          type: "STRING"
        - name: "email"
          type: "STRING"
        - name: "password"
          type: "STRING"
        - name: "phone"
          type: "STRING"
        - name: "userStatus"
          type: "INTEGER"
          format: "INT32"
          description: "User Status"
      ffabfe76-52ec-4bf9-96dd-d309fa424561:
        name: "Tag"
        type: "OBJECT"
        section: "#/contract/sections/b1e53699-68bd-40f8-813e-b50160a723b1"
        properties:
        - name: "id"
          type: "INTEGER"
          format: "INT64"
        - name: "name"
          type: "STRING"
      "3155fb64-434c-44ce-8b29-fa53c78ba12e":
        name: "Pet"
        type: "OBJECT"
        section: "#/contract/sections/b1e53699-68bd-40f8-813e-b50160a723b1"
        properties:
        - name: "id"
          type: "INTEGER"
          format: "INT64"
        - name: "category"
          type: "#/contract/types/50432841-7f7f-499c-a4c4-4cd3ea3cb01a"
        - name: "name"
          type: "STRING"
          required: true
          examples:
          - value: "doggie"
        - name: "photoUrls"
          type: "ARRAY"
          required: true
          items:
            type: "STRING"
        - name: "tags"
          type: "ARRAY"
          items:
            type: "#/contract/types/ffabfe76-52ec-4bf9-96dd-d309fa424561"
        - name: "status"
          type: "STRING"
          description: "pet status in the store"
          enum:
          - "available"
          - "pending"
          - "sold"
      "5bf5f755-2477-408c-a794-9065af536092":
        name: "ApiResponse"
        type: "OBJECT"
        section: "#/contract/sections/b1e53699-68bd-40f8-813e-b50160a723b1"
        properties:
        - name: "code"
          type: "INTEGER"
          format: "INT32"
        - name: "type"
          type: "STRING"
        - name: "message"
          type: "STRING"
  components: {}
api-tryin: |-
  {
    "version" : 6,
    "entities" : [ {
      "entity" : {
        "type" : "Project",
        "name" : "Petstore API 4.1.0",
        "description" : "This is a sample server Petstore server.  You can find out more about Swagger at [http://swagger.io](http://swagger.io) or on [irc.freenode.net, #swagger](http://swagger.io/irc/).  For this sample, you can use the api key `special-key` to test the authorization filters.",
        "importedFrom" : "0280ac6a-2fda-4c44-b4c1-85bdc55e390a"
      },
      "children" : [ {
        "entity" : {
          "type" : "Service",
          "name" : "Pet"
        },
        "children" : [ {
          "entity" : {
            "type" : "Request",
            "id" : "afda4b22-b78a-46a4-abad-351e7f516610",
            "name" : "Finds Pets by tags",
            "description" : "Muliple tags can be provided with comma separated strings. Use tag1, tag2, tag3 for testing.",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/pet/findByTags",
              "query" : {
                "delimiter" : "&",
                "items" : [ {
                  "name" : "tags",
                  "value" : "",
                  "enabled" : true
                } ]
              }
            },
            "method" : {
              "link" : "",
              "name" : "GET"
            },
            "headers" : [ {
              "enabled" : true,
              "name" : "Accept",
              "value" : "application/xml, application/json"
            } ],
            "headersType" : "Form",
            "uriEditor" : true
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "3da4ea0f-146c-494b-b452-e4d4a1b65700",
            "name" : "Finds Pets by status",
            "description" : "Multiple status values can be provided with comma separated strings",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/pet/findByStatus",
              "query" : {
                "delimiter" : "&",
                "items" : [ {
                  "name" : "status",
                  "value" : "",
                  "enabled" : true
                } ]
              }
            },
            "method" : {
              "link" : "",
              "name" : "GET"
            },
            "headers" : [ {
              "enabled" : true,
              "name" : "Accept",
              "value" : "application/xml, application/json"
            } ],
            "headersType" : "Form",
            "uriEditor" : true
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "be380936-7e09-4b4d-a34d-891357031ecc",
            "name" : "Update an existing pet",
            "description" : "",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/pet"
            },
            "method" : {
              "link" : "",
              "name" : "PUT",
              "requestBody" : true
            },
            "headers" : [ {
              "enabled" : true,
              "name" : "Content-Type",
              "value" : "application/json"
            }, {
              "enabled" : false,
              "name" : "Content-Type",
              "value" : "application/xml"
            } ],
            "headersType" : "Form",
            "body" : {
              "bodyType" : "Text",
              "textBody" : ""
            }
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "4567ac19-428f-4c96-87d8-58b879c8a961",
            "name" : "Add a new pet to the store",
            "description" : "",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/pet"
            },
            "method" : {
              "link" : "",
              "name" : "POST",
              "requestBody" : true
            },
            "headers" : [ {
              "enabled" : true,
              "name" : "Content-Type",
              "value" : "application/json"
            }, {
              "enabled" : false,
              "name" : "Content-Type",
              "value" : "application/xml"
            } ],
            "headersType" : "Form",
            "body" : {
              "bodyType" : "Text",
              "textBody" : ""
            }
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "8d94befd-ed55-4181-908b-e342b5231028",
            "name" : "Find pet by ID",
            "description" : "Returns a single pet",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/pet/{petId}"
            },
            "method" : {
              "link" : "",
              "name" : "GET"
            },
            "headers" : [ {
              "enabled" : false,
              "name" : "api_key",
              "value" : "${\"Api_keyHeaderApi_key\"}"
            }, {
              "enabled" : true,
              "name" : "Accept",
              "value" : "application/xml, application/json"
            } ],
            "headersType" : "Form"
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "02c15703-a1a3-47a3-8420-708b6d99d12a",
            "name" : "Updates a pet in the store with form data",
            "description" : "",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/pet/{petId}"
            },
            "method" : {
              "link" : "",
              "name" : "POST",
              "requestBody" : true
            },
            "headers" : [ {
              "enabled" : true,
              "name" : "Content-Type",
              "value" : "application/x-www-form-urlencoded"
            } ],
            "headersType" : "Form",
            "body" : {
              "bodyType" : "Form",
              "formBody" : {
                "items" : [ {
                  "enabled" : false,
                  "name" : "name",
                  "value" : "",
                  "type" : "Text"
                }, {
                  "enabled" : false,
                  "name" : "status",
                  "value" : "",
                  "type" : "Text"
                } ],
                "encoding" : "application/x-www-form-urlencoded"
              }
            }
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "1097797e-06e1-404d-b943-9468fb7cc100",
            "name" : "Deletes a pet",
            "description" : "",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/pet/{petId}"
            },
            "method" : {
              "link" : "",
              "name" : "DELETE"
            },
            "headers" : [ {
              "enabled" : false,
              "name" : "api_key",
              "value" : ""
            } ],
            "headersType" : "Form"
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "8323c0a7-9874-4d3f-87b4-a05db886bf8b",
            "name" : "uploads an image",
            "description" : "",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/pet/{petId}/uploadImage"
            },
            "method" : {
              "link" : "",
              "name" : "POST",
              "requestBody" : true
            },
            "headers" : [ {
              "enabled" : true,
              "name" : "Content-Type",
              "value" : "multipart/form-data"
            }, {
              "enabled" : true,
              "name" : "Accept",
              "value" : "application/json"
            } ],
            "headersType" : "Form",
            "body" : {
              "bodyType" : "Form",
              "formBody" : {
                "items" : [ {
                  "enabled" : false,
                  "name" : "additionalMetadata",
                  "value" : "",
                  "type" : "Text"
                }, {
                  "enabled" : false,
                  "name" : "file",
                  "type" : "File"
                } ],
                "encoding" : "multipart/form-data"
              }
            }
          }
        } ]
      }, {
        "entity" : {
          "type" : "Service",
          "name" : "Store"
        },
        "children" : [ {
          "entity" : {
            "type" : "Request",
            "id" : "3816fac2-73c6-43f8-87e6-4c41270f5051",
            "name" : "Place an order for a pet",
            "description" : "",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/store/order"
            },
            "method" : {
              "link" : "",
              "name" : "POST",
              "requestBody" : true
            },
            "headers" : [ {
              "enabled" : true,
              "name" : "Content-Type",
              "value" : "application/json"
            }, {
              "enabled" : true,
              "name" : "Accept",
              "value" : "application/xml, application/json"
            } ],
            "headersType" : "Form",
            "body" : {
              "bodyType" : "Text",
              "textBody" : ""
            }
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "4e25864c-4acc-4e1a-93f2-e0442f913821",
            "name" : "Find purchase order by ID",
            "description" : "For valid response try integer IDs with value >= 1 and <= 10. Other values will generated exceptions",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/store/order/{orderId}"
            },
            "method" : {
              "link" : "",
              "name" : "GET"
            },
            "headers" : [ {
              "enabled" : true,
              "name" : "Accept",
              "value" : "application/xml, application/json"
            } ],
            "headersType" : "Form"
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "c441e2e1-f24b-4412-8406-36bf165b4f05",
            "name" : "Delete purchase order by ID",
            "description" : "For valid response try integer IDs with positive integer value. Negative or non-integer values will generate API errors",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/store/order/{orderId}"
            },
            "method" : {
              "link" : "",
              "name" : "DELETE"
            },
            "headers" : [ ],
            "headersType" : "Form"
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "db23ec47-776e-49a1-ac0d-2dc69d8b29aa",
            "name" : "Returns pet inventories by status",
            "description" : "Returns a map of status codes to quantities",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/store/inventory"
            },
            "method" : {
              "link" : "",
              "name" : "GET"
            },
            "headers" : [ {
              "enabled" : false,
              "name" : "api_key",
              "value" : "${\"Api_keyHeaderApi_key\"}"
            }, {
              "enabled" : true,
              "name" : "Accept",
              "value" : "application/json"
            } ],
            "headersType" : "Form"
          }
        } ]
      }, {
        "entity" : {
          "type" : "Service",
          "name" : "User"
        },
        "children" : [ {
          "entity" : {
            "type" : "Request",
            "id" : "0150d33b-4014-46b9-b905-aca48cbbbdb9",
            "name" : "Create user",
            "description" : "This can only be done by the logged in user.",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/user"
            },
            "method" : {
              "link" : "",
              "name" : "POST",
              "requestBody" : true
            },
            "headers" : [ {
              "enabled" : true,
              "name" : "Content-Type",
              "value" : "application/json"
            } ],
            "headersType" : "Form",
            "body" : {
              "bodyType" : "Text",
              "textBody" : ""
            }
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "a621bf7e-ee42-4357-b006-be47d4b6a396",
            "name" : "Creates list of users with given input array",
            "description" : "",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/user/createWithArray"
            },
            "method" : {
              "link" : "",
              "name" : "POST",
              "requestBody" : true
            },
            "headers" : [ {
              "enabled" : true,
              "name" : "Content-Type",
              "value" : "application/json"
            } ],
            "headersType" : "Form",
            "body" : {
              "bodyType" : "Text",
              "textBody" : ""
            }
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "c567a413-faac-4769-9b6f-a5997fd8bb22",
            "name" : "Creates list of users with given input array",
            "description" : "",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/user/createWithList"
            },
            "method" : {
              "link" : "",
              "name" : "POST",
              "requestBody" : true
            },
            "headers" : [ {
              "enabled" : true,
              "name" : "Content-Type",
              "value" : "application/json"
            } ],
            "headersType" : "Form",
            "body" : {
              "bodyType" : "Text",
              "textBody" : ""
            }
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "cabbe72f-cf47-45f2-afd1-df8f1091fe15",
            "name" : "Get user by user name",
            "description" : "",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/user/{username}"
            },
            "method" : {
              "link" : "",
              "name" : "GET"
            },
            "headers" : [ {
              "enabled" : true,
              "name" : "Accept",
              "value" : "application/xml, application/json"
            } ],
            "headersType" : "Form"
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "cb31b6f3-c885-42bd-b5a1-d97284acc110",
            "name" : "Updated user",
            "description" : "This can only be done by the logged in user.",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/user/{username}"
            },
            "method" : {
              "link" : "",
              "name" : "PUT",
              "requestBody" : true
            },
            "headers" : [ {
              "enabled" : true,
              "name" : "Content-Type",
              "value" : "application/json"
            } ],
            "headersType" : "Form",
            "body" : {
              "bodyType" : "Text",
              "textBody" : ""
            }
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "2ab881fc-c147-43c7-840f-56dfa5ac4048",
            "name" : "Delete user",
            "description" : "This can only be done by the logged in user.",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/user/{username}"
            },
            "method" : {
              "link" : "",
              "name" : "DELETE"
            },
            "headers" : [ ],
            "headersType" : "Form"
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "03417de3-da55-420b-a440-a46abd542c96",
            "name" : "Logs user into the system",
            "description" : "",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/user/login",
              "query" : {
                "delimiter" : "&",
                "items" : [ {
                  "name" : "username",
                  "value" : "",
                  "enabled" : true
                }, {
                  "name" : "password",
                  "value" : "",
                  "enabled" : true
                } ]
              }
            },
            "method" : {
              "link" : "",
              "name" : "GET"
            },
            "headers" : [ {
              "enabled" : true,
              "name" : "Accept",
              "value" : "application/xml, application/json"
            } ],
            "headersType" : "Form",
            "uriEditor" : true
          }
        }, {
          "entity" : {
            "type" : "Request",
            "id" : "bc470b15-5cdf-4b42-99d4-29ce9b506e72",
            "name" : "Logs out current logged in user session",
            "uri" : {
              "host" : "${\"BaseUrl\"}",
              "path" : "/user/logout"
            },
            "method" : {
              "link" : "",
              "name" : "GET"
            },
            "headers" : [ ],
            "headersType" : "Form"
          }
        } ]
      } ]
    } ],
    "environments" : [ {
      "name" : "Petstore API 4.1.0",
      "importedFrom" : {
        "projectId" : "0280ac6a-2fda-4c44-b4c1-85bdc55e390a"
      },
      "variables" : {
        "12299b6d-90bc-4a58-826e-4cb87d86ba4f" : {
          "name" : "BaseUrl",
          "value" : "http://petstore.swagger.io/v2",
          "enabled" : true,
          "private" : false
        },
        "869ab934-e202-40b0-b72f-f69fc6e2082d" : {
          "name" : "Api_keyHeaderApi_key",
          "value" : "",
          "enabled" : true,
          "private" : true
        }
      }
    } ]
  }
---
