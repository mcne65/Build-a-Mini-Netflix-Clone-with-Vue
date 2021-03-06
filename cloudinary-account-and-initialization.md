# Cloudinary Account and Initialization

Create the `cloudinaryInstance` instance so you can pass it to `VideoPlayer`.

## Create a Cloudinary Account

In the **MANAGEMENT CONSOLE LOGIN** screen, create a [Cloudinary account](https://cloudinary.com/users/login) or, if you have already done so, sign in.

![](https://d2mxuefqeaa7sj.cloudfront.net/s_C4E0BB4A3CA481FA22D9AA6239D953F2B1D94D00408DB28F7AB567E3C6C4DB1A_1521618396504_Screen+Shot+2018-03-21+at+8.46.20+AM.png)

The **Dashboard** is then displayed:

![](https://d2mxuefqeaa7sj.cloudfront.net/s_C4E0BB4A3CA481FA22D9AA6239D953F2B1D94D00408DB28F7AB567E3C6C4DB1A_1521618722441_Screen+Shot+2018-03-21+at+8.48.56+AM.png)

Your credentials are displayed under **Cloud name**, **API Key**, and **API Secret**. You need the cloud name on the client for image requests.

> **Note**: The contents \(images and videos\) in the rest of this lab do not exist in your account. If you need them, note the sources in the browser, download them, and upload them to your server.

## Import the Cloudinary SDKs

Cloudinary offers SDKs that speed up the process. To import them, go to each of the media files and fetch its URL from the Cloudinary Dashboard. This is a manual task and can be tedious for automated tasks. Actually, all you need is the media's public ID, not the full URL.

1. Select any image on your cloud for both the URL and the public ID:

   ![](https://d2mxuefqeaa7sj.cloudfront.net/s_C4E0BB4A3CA481FA22D9AA6239D953F2B1D94D00408DB28F7AB567E3C6C4DB1A_1521619740815_Screen+Shot+2018-03-21+at+9.06.14+AM.png)

2. Import the SDK libraries to your `public/index.html` file by specifying their URLs below the `div` tag:

   ```markup
   <div id="app"></div>
   <link href="https://unpkg.com/cloudinary-video-player/dist/cld-video-player.min.css" rel="stylesheet">
   <script src="https://unpkg.com/cloudinary-core/cloudinary-core-shrinkwrap.min.js" type="text/javascript"></script>
   <script src="https://unpkg.com/cloudinary-video-player/dist/cld-video-player.min.js" type="text/javascript">   </script>
   ```

3. Add a `created` lifecycle method to the `App` object for initializing Cloudinary with your cloud name:

```javascript
created() {
  this.cloudinaryInstance = window.cloudinary.Cloudinary.new({
    cloud_name: 'YOUR CLOUD NAME',
    secure: true
  });
},
```

## Set up a Moive Data Model

Since you do not have any data to show yet and are just working with the defaults, initialize `movie` as an empty object:

```javascript
data() {
  return {
    movie: {},
  }
},
```

So far, so good:

![](https://res.cloudinary.com/christekh/image/upload/v1521675046/Screen_Shot_2018-03-22_at_12.26.46_AM_jph6qh.png)

