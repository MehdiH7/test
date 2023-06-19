# Instagram Content Publishing Automation

This code allows for the automation of publishing content on Instagram using the Instagram Graph API.

## Dependencies is the first thing to modify

- Python 3.x
- requests: A Python library for making HTTP requests.
- time: A Python module for time-related operations.
- json: A Python module for working with JSON data.
- urllib.parse: A Python module for parsing URLs.


## Getting Started now Mohamad is comming
Clone the repository or download the source code.

Create a configuration file named config.json in the same directory as the script. The file should have the following structure:


```
{
  "instagram_business_account_id": "YOUR_BUSINESS_ACCOUNT_ID",
  "access_token": "YOUR_ACCESS_TOKEN"
}

```


Replace YOUR_BUSINESS_ACCOUNT_ID with your Instagram Business Account ID and YOUR_ACCESS_TOKEN with your access token. Make sure to obtain the necessary permissions and generate the access token from the Facebook Developer Dashboard.

Create a parameters file named params.json in the same directory. This file should contain the parameters for each media type you want to publish. An example structure for publishing images:

```
{
  "media_types": {
    "IMAGES": {
      "image_url": "URL_TO_IMAGE",
      "is_carousel_item": false,
      "caption": "YOUR_IMAGE_CAPTION",
      "location_id": "OPTIONAL_LOCATION_ID",
      "user_tags": "OPTIONAL_USER_TAGS",
      "product_tags": "OPTIONAL_PRODUCT_TAGS"
    }
  }
}

```

Adjust the parameters accordingly for your specific use case.

Run the script by executing the following command in the terminal or command prompt:

python script.py


The script will initiate the content publishing process on Instagram based on the provided parameters.


`------------------------------------------------------------------`



# THE KEYS FOR REELS

| KEY       | DESCRIPTION  | MANDATORY  | EXAMPLE  |
|-----------|-----------|-----------|-----------|
| video_url     | Required for videos and reels. Applies only to videos and reels. Path to the video. We cURL the video using the passed-in URL, so it must be on a public server.    | YES   | https://www.sos-tapis.com/wp-content/uploads/2023/06/y2mate.com-Rare-Moments-in-Football-shorts_1080p.mp4    |
| caption     | A caption for the image, video, or carousel. Can include hashtags (example: #crazywildebeest) and usernames of Instagram users (example: @natgeo). @Mentioned Instagram users receive a notification when the container is published. Maximum 2200 characters, 30 hashtags, and 20 @ tags.    | NO    | THIS IS A CAPTION WITH #HASHTAG    |
| audio_name     | For Reels only. Name of the audio of your Reels media. You can only rename once, either while creating a reel or after from the audio page.    | NO    | Forzasys Original Audio - Norway    |
| thumb_offset     | For videos and reels. Location, in milliseconds, of the video or reel frame to be used as the cover thumbnail image. The default value is 0, which is the first frame of the video or reel. For reels, if you specify both cover_url and thumb_offset, we use cover_url and ignore thumb_offset.   | NO   | 5000   |
| share_to_feed     | For Reels only. When true, indicates that the reel can appear in both the Feed and Reels tabs. When false, indicates the reel can only appear in the Reels tab.   | NO   | TRUE  |
| cover_url     | For Reels only. The path to an image to use as the cover image for the Reels tab. We will cURL the image using the URL that you specify so the image must be on a public server. If you specify both cover_url and thumb_offset, we use cover_url and ignore thumb_offset. The image must conform to the specifications for a Reels cover photo.  | NO   | https://www.sos-tapis.com/wp-content/uploads/2023/03/pexels-curtis-adams-7168011.jpg   |
| user_tags     | Required for user tagging. Applies to images and videos. An array of public usernames and x/y coordinates for any public Instagram users who you want to tag in the image. Each object should have the following information: usernames — Required. Public usernames. x — Images only. An optional float that indicates percentage distance from left edge of the published media image. Value must be within 0.0–1.0 range. y — Images only. An optional float that indicates percentage distance from top edge of the published media image. Value must be within 0.0–1.0 range.   | NO  |   USERNAME: 'MESSI'  |
| location_id    | The ID of a Page associated with a location that you want to tag the image or video with. Use the Pages Search API to search for Pages whose names match a search string, then parse the results to identify any Pages that have been created for a physical location. Include the location field in your query and verify that the Page you want to use has location data  | NO  | 1  |


# THE KEYS FOR VIDEO

| KEY  | DESCRIPTION  | MANDATORY  | EXAMPLE  |
|-----------|-----------|-----------|-----------|
| video_url     | Required for videos and reels. Applies only to videos and reels. Path to the video. We cURL the video using the passed-in URL, so it must be on a public server.    | YES    | https://www.sos-tapis.com/wp-content/uploads/2023/06/y2mate.com-Rare-Moments-in-Football-shorts_1080p.mp4    |
| is_coursel_item     | Applies only to images and video. Set to true. Indicates image or video appears in a carousel.   | NO    | TRUE    |
| caption     | A caption for the image, video, or carousel. Can include hashtags (example: #crazywildebeest) and usernames of Instagram users (example: @natgeo). @Mentioned Instagram users receive a notification when the container is published. Maximum 2200 characters, 30 hashtags, and 20 @ tags. Not supported on images or videos in carousels.    | NO   | this the caption for the Image Module    |
| location_id     | The ID of a Page associated with a location that you want to tag the image or video with. Use the Pages Search API to search for Pages whose names match a search string, then parse the results to identify any Pages that have been created for a physical location. Include the location field in your query and verify that the Page you want to use has location data.   | NO   | 1   |
| user_tags     | 	Required for user tagging. Applies to images and videos. An array of public usernames and x/y coordinates for any public Instagram users who you want to tag in the image. Each object should have the following information: usernames — Required. Public usernames.   | NO   | username: messi  |
| product_tags    | Required for product tagging. Applies only to images and videos. An array of objects specifying which product tags to tag the image or video with (maximum of 5; tags and product IDs must be unique).   | NO   | Data product_id:'3231775643511089'  |


# THE KEYS FOR IMAGES

| KEY  | DESCRIPTION  | MANDATORY  | EXAMPLE  |
|-----------|-----------|-----------|-----------|
| image_url    | For images only and required for images. The path to the image. We will cURL the image using the URL that you specify so the image must be on a public server.    | YES    | https://www.sos-tapis.com/wp-content/uploads/2023/03/pexels-curtis-adams-7168011.jpg    |
| is_coursel_item     | Applies only to images and video. Set to true. Indicates image or video appears in a carousel.    | TRUE    |     |
| caption     | A caption for the image, video, or carousel. Can include hashtags (example: #crazywildebeest) and usernames of Instagram users (example: @natgeo). @Mentioned Instagram users receive a notification when the container is published. Maximum 2200 characters, 30 hashtags, and 20 @ tags. Not supported on images or videos in carousels.    | NO    | this the caption for the Image Module"    |
| location_id     | The ID of a Page associated with a location that you want to tag the image or video with. Use the Pages Search API to search for Pages whose names match a search string, then parse the results to identify any Pages that have been created for a physical location. Include the location field in your query and verify that the Page you want to use has location data.    | NO   | 1   |
| user_tags    | 	Required for user tagging. Applies to images and videos. An array of public usernames and x/y coordinates for any public Instagram users who you want to tag in the image. Each object should have the following information: usernames — Required. Public usernames. x — Images only. An optional float that indicates percentage distance from left edge of the published media image. Value must be within 0.0–1.0 range. y — Images only. An optional float that indicates percentage distance from top edge of the published media image. Value must be within 0.0–1.0 range.   | NO   | username:'kevinhart4real', x: 0.5, y: 0.8   |
| product_tags     | Required for product tagging. Applies only to images and videos. An array of objects specifying which product tags to tag the image or video with (maximum of 5; tags and product IDs must be unique). Each object should have the following information: product_id — Required. Product ID. x — Images only. An optional float that indicates percentage distance from left edge of the published media image. Value must be within 0.0–1.0 range. y — Images only. An optional float that indicates percentage distance from top edge of the published media image. Value must be within 0.0–1.0 range.   | NO  | product_id:'3231775643511089',x: 0.5,y: 0.8   |



# THE KEYS FOR IMAGE STORIES

| KEY  | DESCRIPTION  | MANDATORY  | EXAMPLE  |
|-----------|-----------|-----------|-----------|
| image_url     | For images only and required for images. The path to the image. We will cURL the image using the URL that you specify so the image must be on a public server.    | YES    | https://www.sos-tapis.com/wp-content/uploads/2023/03/pexels-curtis-adams-7168011.jpg     |


# THE KEYS FOR VIDEO STORIES

| KEY  | DESCRIPTION  | MANDATORY  | EXAMPLE  |
|-----------|-----------|-----------|-----------|
| video_url     | Required for videos and reels. Applies only to videos and reels. Path to the video. We cURL the video using the passed-in URL, so it must be on a public server.    | YES    | https://www.sos-tapis.com/wp-content/uploads/2023/06/y2mate.com-Rare-Moments-in-Football-shorts_1080p.mp4     |
