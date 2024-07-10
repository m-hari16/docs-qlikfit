# API QlikFit

## Signin
- Endpoint
````sh
[POST] {BASE_URL}/api/v1/auth/signin
````
- Request Body
````json
{
    "email": "wahid@qlikfit.com",
    "password": "secret"
}
````
- Response Body
````json
{
    "success": true,
    "message": "OK",
    "data": {
        "user": {
            "e_id": "Q-240706011720269160",
            "fullName": "Evan Favian",
            "gender": "M",
            "profileType": "ADMIN"
        },
        "accessToken": {
            "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlX2lkIjoiUS0yNDA3MDYwMTE3MjAyNjkxNjAiLCJmdWxsTmFtZSI6IkV2YW4gRmF2aWFuIiwiZ2VuZGVyIjoiTSIsInByb2ZpbGVUeXBlIjoiQURNSU4iLCJpYXQiOjE3MjAzNDcwMjMsImV4cCI6MTcyMjkzOTAyM30.36UKl9xgHR0KAZ4KLYgNoV35GQQCwzJvaLKUViBXL_I",
            "tokenExpiredAt": "2024-08-06 17:10:23"
        }
    }
}
````

## Add Patient
- Endpoint
````sh
[POST] {BASE_URL}/api/v1/patient/new
````
- Header
````json
{
    "X_USER_TOKEN": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlX2lkIjoiUS0yNDA3MDYwMTE3MjAyNjkxNjAiLCJmdWxsTmFtZSI6IkV2YW4gRmF2aWFuIiwiZ2VuZGVyIjoiTSIsInByb2ZpbGVUeXBlIjoiQURNSU4iLCJpYXQiOjE3MjAzNDcwMjMsImV4cCI6MTcyMjkzOTAyM30.36UKl9xgHR0KAZ4KLYgNoV35GQQCwzJvaLKUViBXL_I"
}
````
- Request Body
````json
{
    "fullName": "Roberta Matias",
    "email": "roberta.matias1127@gmail.com",
    "nik": "3525091092990001",
    "phoneNumber": "086785910021",
    "homeAddress": "Jl. KS Tubun No. 68B",
    "gender": "M",
    "maritalStatus": "SINGLE",
    "dateOfBirth": "1991-04-20",
    "bloodGroup": "O"
}
````
- Response Body
````json
{
    "success": true,
    "message": "OK",
    "data": {
        "fullName": "M Iman",
        "email": "iman.like791@gmail.com",
        "nik": "3525091092990001",
        "phoneNumber": "085932066021",
        "homeAddress": "Jl. Merdeka",
        "gender": "M",
        "maritalStatus": "SINGLE",
        "dateOfBirth": "1991-07-01",
        "bloodGroup": "B",
        "e_id": "QF-24070700447870",
        "isActive": true,
        "profileType": "PATIENT",
        "createdBy": {
            "e_id": "Q-240706011720269160"
        },
        "createdAt": "2024-07-07T10:24:30.488Z"
    }
}
````

## List Patient
- Endpoint
````sh
[GET] {BASE_URL}/api/v1/patient/list
````
- Header
````json
{
    "X_USER_TOKEN": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlX2lkIjoiUS0yNDA3MDYwMTE3MjAyNjkxNjAiLCJmdWxsTmFtZSI6IkV2YW4gRmF2aWFuIiwiZ2VuZGVyIjoiTSIsInByb2ZpbGVUeXBlIjoiQURNSU4iLCJpYXQiOjE3MjAzNDcwMjMsImV4cCI6MTcyMjkzOTAyM30.36UKl9xgHR0KAZ4KLYgNoV35GQQCwzJvaLKUViBXL_I"
}
````
- Response Body
````json
{
    "success": true,
    "message": "OK",
    "data": [
        {
            "e_id": "QF-24070700434801",
            "patientProfile": {
                "fullName": "Roberta Matias",
                "email": "roberta.matias1127@gmail.com",
                "nik": "3525091092990001",
                "phoneNumber": "086785910021",
                "homeAddress": "Jl. KS Tubun No. 68B",
                "gender": "M",
                "maritalStatus": "SINGLE",
                "dateOfBirth": "1991-04-20",
                "bloodGroup": "O",
                "e_id": "QF-24070700434801",
                "isActive": true,
                "profileType": "PATIENT",
                "createdBy": {
                    "e_id": "Q-240706011720269160"
                },
                "createdAt": "2024-07-07T06:46:41.492Z"
            },
            "latestDesease": "",
            "isConnectedDevice": false,
            "createdAt": "2024-07-07T06:46:41.544Z"
        },
        {
            "e_id": "QF-24070700447870",
            "patientProfile": {
                "fullName": "M Iman",
                "email": "iman.like791@gmail.com",
                "nik": "3525091092990002",
                "phoneNumber": "085932066021",
                "homeAddress": "Jl. Merdeka",
                "gender": "M",
                "maritalStatus": "SINGLE",
                "dateOfBirth": "1991-07-01",
                "bloodGroup": "B",
                "e_id": "QF-24070700447870",
                "isActive": true,
                "profileType": "PATIENT",
                "createdBy": {
                    "e_id": "Q-240706011720269160"
                },
                "createdAt": "2024-07-07T10:24:30.488Z"
            },
            "latestDesease": "",
            "isConnectedDevice": false,
            "createdAt": "2024-07-07T10:24:30.635Z"
        }
    ]
}
````

## Latest Patient Condition
- Endpoint
````sh
[GET] {BASE_URL}/api/v1/patient/latest-condition
````
- Header
````json
{
    "X_USER_TOKEN": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlX2lkIjoiUS0yNDA3MDYwMTE3MjAyNjkxNjAiLCJmdWxsTmFtZSI6IkV2YW4gRmF2aWFuIiwiZ2VuZGVyIjoiTSIsInByb2ZpbGVUeXBlIjoiQURNSU4iLCJpYXQiOjE3MjAzNDcwMjMsImV4cCI6MTcyMjkzOTAyM30.36UKl9xgHR0KAZ4KLYgNoV35GQQCwzJvaLKUViBXL_I"
}
````
- Response Body
````json
{
    "success": true,
    "message": "OK",
    "data": [
        {
            "e_id": "QF-24070700434801",
            "patientProfile": {
                "fullName": "Roberta Matias",
                "email": "roberta.matias1127@gmail.com",
                "nik": "3525091092990001",
                "phoneNumber": "086785910021",
                "homeAddress": "Jl. KS Tubun No. 68B",
                "gender": "M",
                "maritalStatus": "SINGLE",
                "dateOfBirth": "1991-04-20",
                "bloodGroup": "O",
                "e_id": "QF-24070700434801",
                "isActive": true,
                "profileType": "PATIENT",
                "createdBy": {
                    "e_id": "Q-240706011720269160"
                },
                "createdAt": "2024-07-07T06:46:41.492Z"
            },
            "latestTreatment": "",
            "latestBloodPressure": null,
            "latestHeartRate": null,
            "latestBloodGlucose": null,
            "latestTemperature": null,
            "latestBloodOxygen": null,
            "isConnectedDevice": false,
            "createdAt": "2024-07-07T06:46:41.544Z",
            "updatedAt": "2024-07-07T06:46:41.544Z"
        },
        {
            "e_id": "QF-24070700447870",
            "patientProfile": {
                "fullName": "M Iman",
                "email": "iman.like791@gmail.com",
                "nik": "3525091092990002",
                "phoneNumber": "085932066021",
                "homeAddress": "Jl. Merdeka",
                "gender": "M",
                "maritalStatus": "SINGLE",
                "dateOfBirth": "1991-07-01",
                "bloodGroup": "B",
                "e_id": "QF-24070700447870",
                "isActive": true,
                "profileType": "PATIENT",
                "createdBy": {
                    "e_id": "Q-240706011720269160"
                },
                "createdAt": "2024-07-07T10:24:30.488Z"
            },
            "latestTreatment": "",
            "latestBloodPressure": null,
            "latestHeartRate": null,
            "latestBloodGlucose": null,
            "latestTemperature": null,
            "latestBloodOxygen": null,
            "isConnectedDevice": false,
            "createdAt": "2024-07-07T10:24:30.635Z",
            "updatedAt": "2024-07-07T10:24:30.635Z"
        }
    ]
}
````

## History Visit
- Endpoint
````sh
[GET] {BASE_URL}/api/v1/patient/history-visit/QF-24070700434801
````
- Header
````json
{
    "X_USER_TOKEN": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlX2lkIjoiUS0yNDA3MDYwMTE3MjAyNjkxNjAiLCJmdWxsTmFtZSI6IkV2YW4gRmF2aWFuIiwiZ2VuZGVyIjoiTSIsInByb2ZpbGVUeXBlIjoiQURNSU4iLCJpYXQiOjE3MjAzNDcwMjMsImV4cCI6MTcyMjkzOTAyM30.36UKl9xgHR0KAZ4KLYgNoV35GQQCwzJvaLKUViBXL_I"
}
````
- Response Body
````json
{
    "success": true,
    "message": "OK",
    "data": [
        {
            "_id": "668a5beeb8b3d786e28e9e38",
            "isActive": true,
            "patient": {
                "e_id": "QF-24070700434801",
                "name": "Roberta Matias"
            },
            "doctor": {
                "e_id": "Q-240706031720269160",
                "name": "Ramzi Siregar"
            },
            "treatment": [
                {
                    "code": "0001",
                    "name": "Check Up"
                }
            ],
            "price": {
                "priceTotal": 250000
            },
            "created_by": {
                "e_id": "Q-240706011720269160"
            },
            "createdAt": "2024-06-14T06:46:41.544Z",
            "updatedAt": "2024-06-14T08:46:41.544Z"
        }
    ]
}
````

## History Blood Pressure
- Endpoint
````sh
[GET] {BASE_URL}/api/v1/device/blood-pressure/{e_id}
````
- Header
````json
{
    "X_USER_TOKEN": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlX2lkIjoiUS0yNDA3MDYwMTE3MjAyNjkxNjAiLCJmdWxsTmFtZSI6IkV2YW4gRmF2aWFuIiwiZ2VuZGVyIjoiTSIsInByb2ZpbGVUeXBlIjoiQURNSU4iLCJpYXQiOjE3MjAzNDcwMjMsImV4cCI6MTcyMjkzOTAyM30.36UKl9xgHR0KAZ4KLYgNoV35GQQCwzJvaLKUViBXL_I"
}
````
- Response Body
````json
{
    "success": true,
    "message": "OK",
    "data": [
        {
            "e_id": "QF-24070700434801",
            "systole": 120,
            "diastole": 88,
            "isActive": true,
            "createdBy": {
                "e_id": ""
            },
            "createdAt": "2024-07-07T06:46:41.544Z"
        },
        {
            "e_id": "QF-24070700434801",
            "systole": 123,
            "diastole": 89,
            "isActive": true,
            "createdBy": {
                "e_id": ""
            },
            "createdAt": "2024-07-07T07:06:41.544Z"
        }
    ]
}
````

## History Blood Oxygen
- Endpoint
````sh
[GET] {BASE_URL}/api/v1/device/blood-oxygen/{e_id}
````
- Header
````json
{
    "X_USER_TOKEN": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlX2lkIjoiUS0yNDA3MDYwMTE3MjAyNjkxNjAiLCJmdWxsTmFtZSI6IkV2YW4gRmF2aWFuIiwiZ2VuZGVyIjoiTSIsInByb2ZpbGVUeXBlIjoiQURNSU4iLCJpYXQiOjE3MjAzNDcwMjMsImV4cCI6MTcyMjkzOTAyM30.36UKl9xgHR0KAZ4KLYgNoV35GQQCwzJvaLKUViBXL_I"
}
````
- Response Body
````json
{
    "success": true,
    "message": "OK",
    "data": [
        {
            "e_id": "QF-24070700434801",
            "bloodOxygen": 99,
            "isActive": true,
            "createdBy": {
                "e_id": ""
            },
            "createdAt": "2024-07-07T06:46:41.544Z"
        },
        {
            "e_id": "QF-24070700434801",
            "bloodOxygen": 99,
            "isActive": true,
            "createdBy": {
                "e_id": ""
            },
            "createdAt": "2024-07-07T07:06:41.544Z"
        }
    ]
}
````

## History Blood Glucose
- Endpoint
````sh
[GET] {BASE_URL}/api/v1/device/blood-glucose/{e_id}
````
- Header
````json
{
    "X_USER_TOKEN": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlX2lkIjoiUS0yNDA3MDYwMTE3MjAyNjkxNjAiLCJmdWxsTmFtZSI6IkV2YW4gRmF2aWFuIiwiZ2VuZGVyIjoiTSIsInByb2ZpbGVUeXBlIjoiQURNSU4iLCJpYXQiOjE3MjAzNDcwMjMsImV4cCI6MTcyMjkzOTAyM30.36UKl9xgHR0KAZ4KLYgNoV35GQQCwzJvaLKUViBXL_I"
}
````
- Response Body
````json
{
    "success": true,
    "message": "OK",
    "data": [
        {
            "e_id": "QF-24070700434801",
            "bloodGlucose": 159,
            "isActive": true,
            "createdBy": {
                "e_id": ""
            },
            "createdAt": "2024-07-07T06:46:41.544Z"
        },
        {
            "e_id": "QF-24070700434801",
            "bloodGlucose": 151,
            "isActive": true,
            "createdBy": {
                "e_id": ""
            },
            "createdAt": "2024-07-07T07:06:41.544Z"
        }
    ]
}
````

## History HeartRate
- Endpoint
````sh
[GET] {BASE_URL}/api/v1/device/heart-rate/{e_id}
````
- Header
````json
{
    "X_USER_TOKEN": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlX2lkIjoiUS0yNDA3MDYwMTE3MjAyNjkxNjAiLCJmdWxsTmFtZSI6IkV2YW4gRmF2aWFuIiwiZ2VuZGVyIjoiTSIsInByb2ZpbGVUeXBlIjoiQURNSU4iLCJpYXQiOjE3MjAzNDcwMjMsImV4cCI6MTcyMjkzOTAyM30.36UKl9xgHR0KAZ4KLYgNoV35GQQCwzJvaLKUViBXL_I"
}
````
- Response Body
````json
{
    "success": true,
    "message": "OK",
    "data": [
        {
            "e_id": "QF-24070700434801",
            "heartRate": 80,
            "isActive": true,
            "createdBy": {
                "e_id": ""
            },
            "createdAt": "2024-07-07T06:46:41.544Z"
        },
        {
            "e_id": "QF-24070700434801",
            "heartRate": 81,
            "isActive": true,
            "createdBy": {
                "e_id": ""
            },
            "createdAt": "2024-07-07T07:06:41.544Z"
        }
    ]
}
````

## History Temperature
- Endpoint
````sh
[GET] {BASE_URL}/api/v1/device/temperature/{e_id}
````
- Header
````json
{
    "X_USER_TOKEN": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlX2lkIjoiUS0yNDA3MDYwMTE3MjAyNjkxNjAiLCJmdWxsTmFtZSI6IkV2YW4gRmF2aWFuIiwiZ2VuZGVyIjoiTSIsInByb2ZpbGVUeXBlIjoiQURNSU4iLCJpYXQiOjE3MjAzNDcwMjMsImV4cCI6MTcyMjkzOTAyM30.36UKl9xgHR0KAZ4KLYgNoV35GQQCwzJvaLKUViBXL_I"
}
````
- Response Body
````json
{
    "success": true,
    "message": "OK",
    "data": [
        {
            "e_id": "QF-24070700434801",
            "temperature": 36,
            "isActive": true,
            "createdBy": {
                "e_id": ""
            },
            "createdAt": "2024-07-07T06:46:41.544Z"
        },
        {
            "e_id": "QF-24070700434801",
            "temperature": 36,
            "isActive": true,
            "createdBy": {
                "e_id": ""
            },
            "createdAt": "2024-07-07T07:06:41.544Z"
        }
    ]
}
````