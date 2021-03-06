# Header and Navigation

1. Clean up the `App.vue` file and add headers and navigation to it. That is, replace the content of the `template` file with the following:

   ```markup
   <template>
    <div id="app">
      <nav class="navbar is-fixed-top" role="navigation" aria-label="main navigation">
        <div class="container">
          <div class="navbar-brand">
            <a class="navbar-item" href="/">
              <img src="https://cloudinary-res.cloudinary.com/image/upload/v1521663307/MiniFlix-Logo_620x180.png" alt="Netflix" width="112" height="28">
            </a>
            <div class="navbar-menu">
              <div class="navbar-end">
                <!-- Upload button here -->
              </div>
            </div>
          </div>
        </div>
      </nav>
    </div>
   </template>
   ```

   The above HTML code shows a navigation bar along with the Netflix logo. It also allocates the space for a button for uploading media content.

2. Update the style sheet so that it reads like this:

   ```css
   #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #e5e5e5;
    background-color: #000;
    padding-top: 30px;
   }
   .navbar {
    background-color: transparent;
    z-index: 2;
    padding: 30px 0;
   }
   .navbar-item {
    height: 25px;
    width: auto;
   }
   ```

3. Add the Bulma classes, a CSS framework that simplifies most of your styling tasks, below the `head` tag of the `public/index.html` file:

   ```markup
   <link rel="stylesheet"         href="https://cdnjs.cloudflare.com/ajax/libs/bulma/0.6.2/css/bulma.min.css">
   <script defer src="https://use.fontawesome.com/releases/v5.0.6/js/all.js">   
   </script>
   <title>Netflix</title>
   ```

4. Add Font Awesome and update the title:

![](https://res.cloudinary.com/christekh/image/upload/v1521673663/Screen_Shot_2018-03-22_at_12.06.10_AM_t4ltif.png)

