---
# NOTICE: Copyright 2024 Talend SA, Talend, Inc., and affiliates. All Rights Reserved. Customer’s use of the software contained herein is subject to the terms and conditions of the Agreement between Customer and Talend.
layout: "apiDefinition_1.1.0"
api-definition:
  specVersion: "4.1.0"
  info:
    name: "Student API"
    version: "1.0.0"
    description: "This is the offical API for trusted Student data at our institution."
    contact: {}
  contract:
    baseUrls:
    - url: "https://lp1uhp3.us.api-mocks.com"
      description: "This is your API mock endpoint. When called, it will simulate the behavior of your API."
      isPublished: true
    - url: "http://tal-bhough5520:8040/services/student-api"
      description: "Demo Environment"
      isPublished: true
    unsortedElementOrder:
    - "#/contract/resources/3e395dca-83be-40b2-baa4-6d11a73a49fd"
    - "#/contract/resources/d341eb2b-cb44-44e4-ac9f-86d62e1381f8"
    - "#/contract/types/2cd83d66-5be3-498d-951b-7993b5000d81"
    - "#/contract/types/ed48aef0-0c24-4f17-936b-7d18fbecec02"
    resources:
      "3e395dca-83be-40b2-baa4-6d11a73a49fd":
        path: "/student/{id}/"
        pathVariables:
        - name: "id"
          type: "STRING"
          required: true
        operations:
          eb16b27f-420c-49db-ab0a-fb125d62135b:
            name: "Get by Student ID"
            method: "GET"
            description: "Get Students using the Student ID"
            responses:
              "31925e8a-9774-453e-97fd-9f92477ca47b":
                status: "200"
                description: "Status 200"
                bodies:
                - type: "#/contract/types/ed48aef0-0c24-4f17-936b-7d18fbecec02"
                  mediaTypes:
                  - "application/json"
          "91ae5f3c-864c-4b79-95bf-00fc9c5452ce":
            name: "Delete Student"
            method: "DELETE"
            description: "Delete the student by ID"
            responses:
              "57799be8-f214-46b5-8dc4-ffc26c76e6e1":
                status: "202"
                description: "Status 202"
      d341eb2b-cb44-44e4-ac9f-86d62e1381f8:
        path: "/student/"
        operations:
          c511c381-21b7-49f1-b24e-22c5279f3514:
            name: "Get Students"
            method: "GET"
            queryParameters:
            - name: "applicantStatus"
              type: "STRING"
              description: "Student Applicant Status"
              enum:
              - "accepted"
              - "denied"
              - "withdraw"
              - "enrolled"
            - name: "lastName"
              type: "STRING"
              description: "Student Last Name"
              maxLength: 50
              examples:
              - value: "Jones"
              - value: "Smith"
              - value: "Johnson"
              - value: "Ramirez"
              - value: "Iglesias"
              - value: "Hernandez"
            - name: "entryTerm"
              type: "STRING"
              description: "Student Entry Term"
              minLength: 6
              maxLength: 6
              examples:
              - value: "201801"
              - value: "201901"
              - value: "202001"
              - value: "202101"
              - value: "202401"
              - value: "202402"
              - value: "202403"
            - name: "firstName"
              type: "STRING"
              description: "Student First Name"
              maxLength: 50
              examples:
              - value: "John"
              - value: "Amy"
              - value: "George"
            responses:
              "082242fe-d636-45b7-8a39-f9742a771961":
                status: "200"
                description: "Status 200"
                bodies:
                - type: "ARRAY"
                  items:
                    type: "#/contract/types/ed48aef0-0c24-4f17-936b-7d18fbecec02"
                  examples:
                  - value: "{  \n   \"student\":[  \n      {  \n         \"studentId\":145003,\n         \"firstName\":\"Benjamin\",\n         \"middleName\":\"Woodrow\",\n         \"lastName\":\"Fillmore\",\n         \"applicantStatus\":\"withdraw\",\n         \"entryTerm\":201702,\n         \"address\":\"539 Cleveland Ave.\",\n         \"city\":\"Helena\",\n         \"state\":\"Mississippi\",\n         \"zip\":3657\n      },\n      {  \n         \"studentId\":145013,\n         \"firstName\":\"Andrew\",\n         \"middleName\":\"Warren\",\n         \"lastName\":\"Fillmore\",\n         \"applicantStatus\":\"accepted\",\n         \"entryTerm\":201701,\n         \"address\":\"1229 Bailard Avenue\",\n         \"city\":\"Trenton\",\n         \"state\":\"South Carolina\",\n         \"zip\":63959\n      },\n      {  \n         \"studentId\":145091,\n         \"firstName\":\"Millard\",\n         \"middleName\":\"Richard\",\n         \"lastName\":\"Fillmore\",\n         \"applicantStatus\":\"enrolled\",\n         \"entryTerm\":201701,\n         \"address\":\"1090 Carpinteria North\",\n         \"city\":\"Providence\",\n         \"state\":\"Maine\",\n         \"zip\":57472\n      }\n   ]\n}"
                  mediaTypes:
                  - "application/json"
          "2f9c7f34-fa22-4da4-b0f1-960f465265d3":
            name: "Add a new Student"
            method: "POST"
            bodies:
            - type: "#/contract/types/ed48aef0-0c24-4f17-936b-7d18fbecec02"
              examples:
              - value: |-
                  {
                    "student": {
                      "studentId": 55555,
                      "firstName": "Andrew",
                      "middleName": "Franklin",
                      "lastName": "Quincy",
                      "applicantStatus": "accepted",
                      "entryTerm": 201702,
                      "address": "1793 East Main Street",
                      "city": "Columbia",
                      "state": "Hawaii",
                      "zip": 62433
                    }
                  }
              mediaTypes:
              - "application/json"
            responses:
              "2d409935-049b-45df-b86c-5bf5bd7f5eb5":
                status: "200"
                description: "Status 200"
    types:
      "2cd83d66-5be3-498d-951b-7993b5000d81":
        name: "applicantStatus"
        type: "STRING"
        description: "The Student Applicant Status"
        enum:
        - "accepted"
        - "denied"
        - "withdraw"
        - "enrolled"
      ed48aef0-0c24-4f17-936b-7d18fbecec02:
        name: "Student JSON"
        type: "OBJECT"
        description: "Student JSON Structure"
        properties:
        - name: "Student"
          type: "OBJECT"
          properties:
          - name: "zip"
            type: "NUMBER"
            description: "Postal Code"
          - name: "city"
            type: "STRING"
            maxLength: 50
          - name: "state"
            type: "STRING"
            description: "State, Province, etc."
            minLength: 2
            maxLength: 2
          - name: "address"
            type: "STRING"
            description: "Street address"
          - name: "lastName"
            type: "STRING"
            maxLength: 50
          - name: "entryTerm"
            type: "NUMBER"
            examples:
            - value: 201701
          - name: "firstName"
            type: "STRING"
            maxLength: 50
          - name: "studentId"
            type: "NUMBER"
            examples:
            - value: 145001
          - name: "middleName"
            type: "STRING"
            maxLength: 50
          - name: "applicantStatus"
            type: "#/contract/types/2cd83d66-5be3-498d-951b-7993b5000d81"
        examples:
        - value: |-
            {
              "student": {
                "studentId": 145025,
                "firstName": "Andrew",
                "middleName": "Franklin",
                "lastName": "Quincy",
                "applicantStatus": "accepted",
                "entryTerm": 201702,
                "address": "1793 East Main Street",
                "city": "Columbia",
                "state": "Hawaii",
                "zip": 62433
              }
            }
  components:
    pathVariables:
      "619e3935-e7f8-431c-ae97-9258e5afc441":
        name: "studentId"
        componentName: "studentId"
        type: "INTEGER"
        format: "INT32"
        description: "The Student ID"
        required: true
        examples:
        - value: 44444
api-tryin: |-
  {
    "version" : 6,
    "entities" : [ {
      "entity" : {
        "type" : "Project",
        "name" : "Student API 1.0.0",
        "description" : "This is the offical API for trusted Student data at our institution.",
        "importedFrom" : "9d0f92c5-3e33-4622-a719-72d01791f7b5"
      },
      "children" : [ {
        "entity" : {
          "type" : "Request",
          "id" : "eb16b27f-420c-49db-ab0a-fb125d62135b",
          "name" : "Get by Student ID",
          "description" : "Get Students using the Student ID",
          "uri" : {
            "host" : "${\"BaseUrl\"}",
            "path" : "/student/{id}/"
          },
          "method" : {
            "link" : "",
            "name" : "GET"
          },
          "headers" : [ {
            "enabled" : true,
            "name" : "Accept",
            "value" : "application/json"
          } ],
          "headersType" : "Form"
        }
      }, {
        "entity" : {
          "type" : "Request",
          "id" : "91ae5f3c-864c-4b79-95bf-00fc9c5452ce",
          "name" : "Delete Student",
          "description" : "Delete the student by ID",
          "uri" : {
            "host" : "${\"BaseUrl\"}",
            "path" : "/student/{id}/"
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
          "id" : "c511c381-21b7-49f1-b24e-22c5279f3514",
          "name" : "Get Students",
          "uri" : {
            "host" : "${\"BaseUrl\"}",
            "path" : "/student/",
            "query" : {
              "delimiter" : "&",
              "items" : [ {
                "name" : "applicantStatus",
                "value" : "accepted",
                "enabled" : false
              }, {
                "name" : "lastName",
                "value" : "Jones",
                "enabled" : false
              }, {
                "name" : "entryTerm",
                "value" : "201801",
                "enabled" : false
              }, {
                "name" : "firstName",
                "value" : "John",
                "enabled" : false
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
            "value" : "application/json"
          } ],
          "headersType" : "Form",
          "uriEditor" : true
        }
      }, {
        "entity" : {
          "type" : "Request",
          "id" : "2f9c7f34-fa22-4da4-b0f1-960f465265d3",
          "name" : "Add a new Student",
          "uri" : {
            "host" : "${\"BaseUrl\"}",
            "path" : "/student/"
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
            "textBody" : "{\n  \"student\": {\n    \"studentId\": 55555,\n    \"firstName\": \"Andrew\",\n    \"middleName\": \"Franklin\",\n    \"lastName\": \"Quincy\",\n    \"applicantStatus\": \"accepted\",\n    \"entryTerm\": 201702,\n    \"address\": \"1793 East Main Street\",\n    \"city\": \"Columbia\",\n    \"state\": \"Hawaii\",\n    \"zip\": 62433\n  }\n}"
          }
        }
      } ]
    } ],
    "environments" : [ {
      "name" : "Student API 1.0.0",
      "importedFrom" : {
        "projectId" : "9d0f92c5-3e33-4622-a719-72d01791f7b5"
      },
      "variables" : {
        "e95589d3-a480-4139-9810-54a9a6684915" : {
          "name" : "BaseUrl",
          "value" : "https://lp1uhp3.us.api-mocks.com",
          "enabled" : true,
          "private" : false
        }
      }
    }, {
      "name" : "Student API 1.0.0",
      "importedFrom" : {
        "projectId" : "9d0f92c5-3e33-4622-a719-72d01791f7b5"
      },
      "variables" : {
        "3becd7a0-82c2-4e14-8b61-8ca1e078454b" : {
          "name" : "BaseUrl",
          "value" : "http://tal-bhough5520:8040/services/student-api",
          "enabled" : true,
          "private" : false
        }
      }
    } ]
  }
---
