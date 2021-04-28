## Track Document Viewer screen
**Page Link** : http://api.creditnirvana.tk:3000/viewPager?doc_id=436
### <u>Add Track View Status Info</u>

**Method** : POST

**URL** : "https://607e8a4c02a23c0017e8b848.mockapi.io/TrackViewerStatus"

**REQUEST PAYLOAD** :

```
{

        "ipAddress":"",

        "openDate":"20/04/2021",

        "openTime":"20:11:28",

        "sessionDuration":"0hr 0min 0sec",

        "scrolledTillEnd":"no",

        "s3BucketId":436

    }
   ```
  **RESPONSE**:
  ```
  {

        id: "2",

        ipAddress: "",

        openDate: "20/04/2021",

        openTime: "20:11:28",

        s3BucketId: 436,

        scrolledTillEnd: "no",

        sessionDuration: "0hr 0min 0sec"

    }
  ```
  **Note**: Needed table unique id for update

### <u>Update Track View Status Info</u>

**Method** : PUT

**URL** :

"https://607e8a4c02a23c0017e8b848.mockapi.io/TrackViewerStatus"

**REQUEST PAYLOAD** :

```
 {

        id: "2",

        ipAddress: "42.111.145.157",

        openDate: "20/04/2021",

        openTime: "20:11:28",

        s3BucketId: 436,

        scrolledTillEnd: "yes",

        sessionDuration: "0hr 0min 33sec"

    }

