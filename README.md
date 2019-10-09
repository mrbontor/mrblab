# API

### _**DOCUMENTATION**_
* [CRUD CAMPAIGN](#crudcampaign)
* [PASIEN RAWAT INAP](#pasienInap)
* [PASIEN RAWAT JALAN](#pasienJalan)
* [PASIEN RAWAT DARURAT](#pasienDarurat)
* [ADMISSION](#admission)
* [RUJUKAN](#rujukan)



# INFLUENCER-CAMPAIGN-TRANSACTIONS
CAMPAIGN TRANSACTIONS

> _**LIST RC**_

* *0000* `==>` *Payment Successful*
* *0010* `==>` *user not found*
* *0020* `==>` *require form validation*
* *0030* `==>` *account has been disactivated or blocked by administrator*
* *0040* `==>` *campaign has claimed*
* *0050* `==>` *user have no right to claim this campaign, cuz level or coorporates trying to claim their's product by self*
* *0060* `==>` *product or campaign not found*
* *0070* `==>` *product or campaign expired*
* *0080* `==>` *this error come while faild generating media or something error in server*
* *0090* `==>` *check IG post is the latest or Up-to-date*
* *0100* `==>` *Tags or Mentions are not found*
* *0200* `==>` *Payment Failed*


> ## _**LIST URI**_

* *POST*    http://localhost:52005/transaction  >>> `User (influencer|coorporate) claim campaign from user coorporate`
```
body :
{
	"id": "string",
	"coorporate": "string",
	"username": "string",
	"media": "string"
}
```

* *POST*    http://localhost:52005/list-order  >>> `show list campaign transactions as host (coorporate)`
```
body :
{
    username: "string"
}

filter list trx by status

body :
{
    username": "string",
    status: "string"
}

```

* *POST*    http://localhost:52005/list-claim  >>> `show list campaign transactions as guest (influencer | coorporate)`
```
body :
{
    username: "string"
}

filter list trx by status

body :
{
    username": "string",
    status: "string"
}

```
<a name="crudcampaign" />
* *GET*    http://localhost:52005/claimed/:coorporate  >>> `show all transaction as coorporate`
```
body :
{
    "username": "string",
}
```

* *GET*    http://localhost:52005/media-recent  >>> `generate media from instagram instead by guest(influencer | coorporate)`
```
body :
{
    "username`": "string",
}
```

* *POST*    http://localhost:52005/check-campaign-trx  >>> `get campaign detail transaction`
```
body :
{
    "uid"        : "string",
    "username"  : "string",
}
