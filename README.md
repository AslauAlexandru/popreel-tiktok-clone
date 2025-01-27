# Week 11 Headstarter Accelerator Project 11 Popreel: TikTok Clone

## App Setup (localhost)

```
git clone https://github.com/AslauAlexandru/popreel-tiktok-clone
cd popreel-tiktok-clone
cp .env.example .env
```


You'll have to set up an AppWrite account, and then add all of the details into your .env file.

For example .env.example looks like:
```
NEXT_PUBLIC_APPWRITE_URL='https://cloud.appwrite.io/v1'
NEXT_PUBLIC_ENDPOINT=''
NEXT_PUBLIC_DATABASE_ID=''

NEXT_PUBLIC_COLLECTION_ID_PROFILE=''
NEXT_PUBLIC_COLLECTION_ID_POST=''
NEXT_PUBLIC_COLLECTION_ID_LIKE=''
NEXT_PUBLIC_COLLECTION_ID_COMMENT=''

NEXT_PUBLIC_BUCKET_NAME="tiktok-clone"
NEXT_PUBLIC_BUCKET_ID=''
NEXT_PUBLIC_PLACEHOLDER_DEAFULT_IMAGE_ID=''

```

## AppWrite Schema

### Database Name: tiktok-clone

### Profile Collection:
| Key | Type |
| --- | --- |
| `Document ID` | String |
| `image` | String |
| `bio` | String |
| `user_id` | String |
| `name` | String |

Profile Indexes:
| KEY           | TYPE          | ATTRIBUTE     | ASC/DESC      |
| ------------- | ------------- | ------------- | ------------- |
| user_id       | key           | user_id       | asc           |
| name          | fulltext      | name          | asc           |

Profile Settings (Update Permissions):
| Add Role      | PERMISSIONS   |
| ------------- | ------------- |
| All guests    | Read          |
| All users     | Create, Read, Update, Delete |

### Post Collection:
| Key | Type |
| --- | --- |
| `Document ID` | String |
| `user_id` | String |
| `video_url` | String |
| `text` | String |
| `created_at` | String |
    
Post Indexes:
| KEY           | TYPE          | ATTRIBUTE     | ASC/DESC      |
| ------------- | ------------- | ------------- | ------------- |
| user_id       | key           | user_id       | asc           |

Profile Settings (Update Permissions):
| Add Role      | PERMISSIONS   |
| ------------- | ------------- |
| All guests    | Read          |
| All users     | Create, Read, Update, Delete |

### Like Collection:
| Key | Type |
| --- | --- |
| `Document ID` | String |
| `user_id` | String |
| `post_id` | String |

Like Indexes: 
| KEY           | TYPE          | ATTRIBUTE     | ASC/DESC      |
| ------------- | ------------- | ------------- | ------------- |
| user_id       | key           | user_id       | asc           |
| id            | unique        | id            | asc           |
| post_id       | key           | post_id       | asc           |

Like Settings (Update Permissions):
| Add Role      | PERMISSIONS   |
| ------------- | ------------- |
| All guests    | Read          |
| All users     | Create, Read, Update, Delete |

### Comment Collection:
| Key | Type |
| --- | --- |
| `Document ID` | String |
| `user_id` | String |
| `post_id` | String |
| `text` | String |
| `created_at` | String |
    
Comment Indexes:
| KEY           | TYPE          | ATTRIBUTE     | ASC/DESC      |
| ------------- | ------------- | ------------- | ------------- |
| post_id       | key           | post_id       | asc           |

Comment Settings (Update Permissions):
| Add Role      | PERMISSIONS   |
| ------------- | ------------- |
| All guests    | Read          |
| All users     | Create, Read, Update, Delete |


Once you've connected your application to AppWrite. Run the commands.
    
```
npm i

npm run dev
```



