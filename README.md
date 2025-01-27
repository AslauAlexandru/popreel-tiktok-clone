# Week 11 Headstarter Accelerator Project 11 Popreel: TikTok Clone

## Project statement
*I don't implement a smart recommendation system for what videos a user sees on their feed and I have not done the challenges.*

PopReel: TikTok Clone.
For this project, you are tasked with building a platform where users can create and share short-form video content, like TikTok.


For this project, imagine you are an engineer at a social media startup. You are tasked with building out a platform where users can create, share, and discover short-form video content, just like TikTok.

**Project Requirements:**

- Build a full-stack web app where users can post short-form videos and view videos from others in a feed
- Allow users to like and comment on videos, and let them share and favorite videos
- Implement a smart recommendation system for what videos a user sees on their feed

**Challenges:**

- Implement a moderation system to prevent users from uploading inappropriate content
- Make your recommendation system adaptive based on the user's most recent activity
- Ensure minimal latency in the video uploads and playback



### Resources
[TikTok's Recommendation System](
https://arxiv.org/pdf/2209.07663)

[How TikTok Recommends Content](
https://support.tiktok.com/en/using-tiktok/exploring-videos/how-tiktok-recommends-content)

[Next JS Video Optimization](
https://nextjs.org/docs/app/building-your-application/optimizing/videos)

[Adding Videos to a Next JS App](
https://next-video.dev/)

[User Onboarding Flow with Clerk](
https://clerk.com/docs/references/nextjs/add-onboarding-flow)

[Example Book Recommendation System](
https://github.com/weaviate/BookRecs)

[Next JS Auth Starter Template](
https://github.com/clerk/nextjs-auth-starter-template)



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
Important resource and important reference, you can check this [video here](https://www.youtube.com/watch?v=7zLyVzItZlQ).

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





