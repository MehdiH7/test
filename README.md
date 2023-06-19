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



# THE KEYS FOR IMAGE STORIES

| KEY  | DESCRIPTION  | MANDATORY  | EXAMPLE  |
|-----------|-----------|-----------|-----------|
| image_url     | For images only and required for images. The path to the image. We will cURL the image using the URL that you specify so the image must be on a public server.    | YES    | https://www.sos-tapis.com/wp-content/uploads/2023/03/pexels-curtis-adams-7168011.jpg     |


# THE KEYS FOR VIDEO STORIES

| KEY  | DESCRIPTION  | MANDATORY  | EXAMPLE  |
|-----------|-----------|-----------|-----------|
| video_url     | Required for videos and reels. Applies only to videos and reels. Path to the video. We cURL the video using the passed-in URL, so it must be on a public server.    | YES    | https://www.sos-tapis.com/wp-content/uploads/2023/06/y2mate.com-Rare-Moments-in-Football-shorts_1080p.mp4     |
