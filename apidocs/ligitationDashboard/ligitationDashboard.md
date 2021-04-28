
## Dashboard screen

  
**Page Link**: http://api.creditnirvana.tk:3000/home/Collections
### <u>Get all cases against caseTypeId</u>

**Method** : GET

**URL** : "https://607cb0f0184368001769c732.mockapi.io/ligitationDashboard?caseTypeId=1"

**RESPONSE** :

```

[

{

"total_cases": 6,

"total_tatBreached": 2,

"total_pending": 0,

"steps": [

{

"stepId": 1,

"stepName": "notice intitated"

},

{

"stepId": 2,

"stepName": "warning notice",

"inProgress": 3,

"pending": 2,

"tatBreached": 1

},

{

"stepId": 3,

"stepName": "Resending Warning notice",

"inProgress": 0,

"pending": 0,

"tatBreached": 2

},

{

"stepId": 4,

"stepName": "Filing court petition",

"inProgress": 0,

"pending": 0,

"tatBreached": 0

}

]

}

]

```

## Section screen

### <u>Track Cases Status</u>

**Method** : POST

**URL** : "https://607cb0f0184368001769c732.mockapi.io/trackCaseStatus"

-  **1) REQUEST PAYLOAD** : (All Available Cases)

```

{

caseTypeId : 2

stepId : null,

actionType:null

}

```

-  **2) REQUEST PAYLOAD** : (All Available Cases against actionType)

```

{

caseTypeId : 2

stepId : null,

actionType: 'pending' | 'inProgress' | 'tatBreached'

}

```

-  **3) REQUEST PAYLOAD** : (All Available Cases against step)

```

{

caseTypeId : 2

stepId : 2,

actionType: null

}

```

-  **4) REQUEST PAYLOAD** : (All Available Cases against step and actionType)

```

{

caseTypeId : 2

stepId : 2,

actionType: 'pending' | 'inProgress' | 'tatBreached'

}

```

**RESPONSE** (show only active cases):

```

[

{

"id": 1,

"loanId": "LSB215",

"applicantName": "Ashwin",

"caseId": "CI1456",

"state": "TAT Breached",

"caseInfoId": 2,

"nextStep": "Resending Warning notice",

"isActive":true

},

{

"id": 2,

"loanId": "LSB215",

"applicantName": "Ashwin",

"caseId": "CI1456",

"caseInfoId": null,

"state": "Pending",

"nextStep": "warning notice",

"isActive":true

},

{

"id": 3,

"loanId": "LSB215",

"applicantName": "Ashwin",

"caseId": "CI1456",

"caseInfoId": 1,

"state": "InProgess",

"nextStep": "warning notice",

"isActive":true

}

]

```

### <u>Move to next step</u>

**Method** : PUT

**URL** : "https://607cb0f0184368001769c732.mockapi.io/trackCaseStatus"

**REQUEST PAYLOAD** :

```

{

caseTypeId : 4,

caseId : 12

}

```

**RESPONSE** : CASES SUCCESSFULLY MOVED TO NEXT STEP

## Cases Info

### <u>Add Case Info</u>

**Method** : POST

**URL** : "https://607cb0f0184368001769c732.mockapi.io/trackCaseStatus"

**REQUEST PAYLOAD** :
```

{

"id": 1,

"caseId":1234,

"courtName": "Alandur High Court",

"judgeName": "Shanmuga Sundaram",

"courtRoom": 13,

"lawyerName": "Ravikiran",

"lawyerEmail": "proraviki@gmail.com"

}

```

  

### <u>Update Case Info</u>

**Method** : PUT

**URL** : "https://607cb0f0184368001769c732.mockapi.io/trackCaseStatus"

**REQUEST PAYLOAD** :

```

{

"id": 1,

"caseId":1234,

"courtName": "Alandur High Court",

"judgeName": "Shanmuga Sundaram",

"courtRoom": 13,

"lawyerName": "Ravikiran",

"lawyerEmail": "proraviki@gmail.com"

}

```

### <u>Get Case Info</u>

**Method** : GET

**URL** :

"https://607cb0f0184368001769c732.mockapi.io/trackCaseStatus?caseId=1234"

**RESPONSE** :

```

{

"id": 1,

"caseId":1234,

"courtName": "Alandur High Court",

"judgeName": "Shanmuga Sundaram",

"courtRoom": 13,

"lawyerName": "Ravikiran",

"lawyerEmail": "proraviki@gmail.com"

}

```

## View Indivual cases Reminders triggers

  

### <u>Get Active Remainders</u>

**METHOD** : POST

**URL** : https://607cb0f0184368001769c732.mockapi.io/trackRemainder?isActive=true

-  **1) REQUEST PAYLOAD** :

```

{

caseTypeId:2,

caseId:12,

isActive:true | false

}

```

-  **2)REQUEST PAYLOAD** :

```

{

caseTypeId:2,

caseId:null,

isActive:true | false

}

```

**RESPONSE**:

```

[

{

"id": "12",

"triggerDate": "22-Feb-2019",

"loanId": "215",

"applicateName": "Bala",

"caseId": "1456",

"activeStage": "Warning Notice",

"nextStage": "Stage Remainder",

"remainderStatus": "TAT Breached",

"isActive": true

},

{

"id": "129",

"triggerDate": "01-Jan-2020",

"loanId": "215",

"applicateName": "Ashwin",

"caseId": "456",

"activeStage": "Legal Notice Intiated",

"nextStage": "Warning Notice",

"remainderStatus": "Stage Remainder",

"isActive": true

},

{

"id": "125",

"triggerDate": "22-Feb-2020",

"loanId": "215",

"applicateName": "Vardhaman",

"caseId": "456",

"activeStage": "Warning Notice",

"nextStage": "Legal Notice Intiated",

"remainderStatus": "TAT Breached",

"isActive": true

}

]

```

### <u>Get Inactive Remainders</u>

**METHOD** : GET

**URL** : https://607cb0f0184368001769c732.mockapi.io/trackRemainder?isActive=true

**RESPONSE**:

```

[

{

"id": "125",

"triggerDate": "22-Feb-2020",

"loanId": "215",

"applicateName": "Ravi",

"caseId": "456",

"activeStage": "Warning Notice",

"nextStage": "",

"remainderStatus": "Stage Remainder",

"isActive": false

}

]

```

  

### <u>Turn Remainders Inactive</u>

**METHOD** : PUT

**URL** : https://607cb0f0184368001769c732.mockapi.io/trackRemainder

**Response** Remainder successfully dismissed
