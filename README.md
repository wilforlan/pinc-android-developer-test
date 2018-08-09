# Android Developer Test

You are required to build out the screen

- Android_feed.png

Icons and sample images are being provided as part of the design test.
You will be required to build out a simple login interface for sample user. Sample user login details:

email: `esther@gmail.com`
password: `password`

After Successfull Authentication, response header will include the following
`access-token, client, uid ` which will then be passed to every other request as an header like so

```
{
    access-token: xxxxxxx,
    client: xxxxx,
    uid: xxxx@something.com
}
```

Sample  Screen for this user when logged in should look like so:

![Alt text](https://s3.us-west-2.amazonaws.com/pinc-test-data/developer-tests/sample_screen_esther.png)


#### API Request

  - Base URL: `https://api.divercity.io/api`
  
###### API Usage/Documentation
To load communities for the top overflowing ( Featured Communities )
Auth Header Required
`GET /group_of_interests`
Sample Response
```
{
    "data": [
        {
            "id": "177",
            "type": "group_of_interests",
            "attributes": {
                "title": "Ruby on Rails Developers Nigeria ",
                "state": "visible",
                "color": "#ff0000",
                "followers_count": 3,
                "questions_count": 1,
                "answers_count": 1,
                "is_followed_by_current": true,
                "picture_main": "https://pinc-backend.s3.amazonaws.com/images/group_of_interests/pictures/000/000/177/original/Ruby_on_Rails_Developers_Nigeria__image.jpg?1533605167",
                "description": "AcommunityforRubyonRailsdeveloperstodiscussandrelatethingspertainingtoRubyonRailsinNigeria",
                "created_at": 1533604945,
                "author_info": {
                    "id": 1171,
                    "present": true,
                    "avatar_thumb": "https://pinc-backend.s3.amazonaws.com/images/users/avatars/000/001/171/thumb/data?1513865642",
                    "avatar_medium": "https://pinc-backend.s3.amazonaws.com/images/users/avatars/000/001/171/medium/data?1513865642",
                    "name": "Aailliams Isaac",
                    "last_name": null
                },
                "group_type": "public",
                "request_to_join_status": "none",
                "is_current_user_admin": true,
                "current_user_admin_level": "super_admin",
                "last_activity_info": [
                    {
                        "author_info": {
                            "id": 1171,
                            "present": true,
                            "avatar_thumb": "https://pinc-backend.s3.amazonaws.com/images/users/avatars/000/001/171/thumb/data?1513865642",
                            "avatar_medium": "https://pinc-backend.s3.amazonaws.com/images/users/avatars/000/001/171/medium/data?1513865642",
                            "name": "Aailliams Isaac",
                            "last_name": null,
                            "nickname": "aailliams_isaac"
                        },
                        "question_info": {
                            "id": 995,
                            "text": "How can I implement searching on Rails API ?",
                            "created_at": "2018-08-07T01:31:29.207Z",
                            "picture_main": "https://pinc-backend.s3.amazonaws.com/images/questions/pictures/000/000/995/main/How_c.jpg?1533605488",
                            "latest_answer": {
                                "id": 2080,
                                "text": "Pretty simple, you can use pg_search, it supports full text, trigrams, and fuzzy search, really an awesome gem",
                                "author_info": {
                                    "id": 1401,
                                    "present": true,
                                    "avatar_thumb": "https://apinew.pincapp.com/images/default_avatar.png",
                                    "avatar_medium": "https://apinew.pincapp.com/images/default_avatar.png",
                                    "name": "Esther Abosede",
                                    "last_name": null,
                                    "nickname": "esther_abosede"
                                }
                            }
                        }
                    }
                ],
                "unseen_message_count": 1,
                "last_question_activity_date": "2018-08-07T01:31:29.207Z"
            }
        },
        ... more 
    }
```

Getting the list of communities to display

Auth Header Required
`GET /group_of_interests/following`
This will return a list of group of interest that the user is currently following.
Sample response is same as above

> Image: `attributes.picture_main`

> Name: `attributes.title`

> Time: `attributes.last_activity_info[0].question_info.created_at`

> Text Info/Summary: `attributes.last_activity_info[0].question_info.latest_answer.author_info.name + last_activity_info[0].question_info.latest_answer.text`

> Unseen Message Count: `attributes.unseen_message_count`









