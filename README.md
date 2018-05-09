

## Running locally

Serve folder with your server of choice. For instance `npm install -g serve`.

# Project Information :

## What is a PWA ?
PWA'S (Progressive Web apps)
Well in layman language it is just converting your awesome website into a Web Application which can be easily be installable on your platform such as windows, android, ios very easily. 
The new generation power which will eradicate the use of native apps from your desktop and from your phones. Progressive Web Apps are experiences that combine the best of the web and the best of apps. They are useful to users from the very first visit in a browser tab, no install required. As the user progressively builds a relationship with the app over time, it becomes more and more powerful. It loads quickly, even on flaky networks, sends relevant push notifications, has an icon on the home screen, and loads as a top-level, full screen experience.
The running engine it uses is your browser to run your site which is i think understandable ;) as it is web app not a native app :D
## Who started it ?
Invented by Google in 2015, Progressive web apps (PWAs) are websites built with the features of both traditional websites and native mobile applications.
The main advantages of Progressive web apps are the capability to work both online and offline, incredible performance that combines the best of websites and mobile applications and easy installation in the user’s device.
Features a PWA has:
Progressive
Responsive
Connectivity independent
App-like
Fresh
Safe : served via https
Discoverable
Re-engageable
Instabble
Linkable
# There 3 things  just add to  your website and you are ready to receive fastest experience of your website.
## Service Workers
Service workers are scripts that offer excellent caching capabilities, offline functionality, push notifications, background synchronizations and so on. They run in the background in the user’s browser and interact with the client’s browser page and HTTP/Get/Post/Set requests. Developers make use of service workers to build Progressive web apps.
They do this by intercepting the requests of users, and sending them through the original end point or changing them to suit different kinds of requirements. Service workers let you enhance the performance of the website through HTTP/2 Push. Additionally, it is also possible for you to write separate codes for new users so that they can fetch cached content and app cache.
Generate your service worker file      https://www.pwabuilder.com/
Service worker follows a lifecycle. To dive deep visit https://developers.google.com/web/fundamentals/primers/service-workers/
## Web Manifests
The main function of Progressive web apps is to provide seamless app experience. Through web manifest, you can provide information about the application in a JSON text file. The web applications are installed on the home screen of a device letting users enjoy quick access.
The users doesn’t have to install anything or go through app stores; they also receive push notifications along with other online capabilities as well. The code for deploying web app manifests in the HTML pages with the help of a link tag goes like this - <link rel="manifest" href="/manifest.json">
Generate your Manifest file here : https://app-manifest.firebaseapp.com/
## Valid secure HTTPS connection
The service worker you install in your site will only register itself on a secured https connection. As, the service worker is responsible for caching all the files, push notifications, content updates, data handling and much more.
It is important to understand that this script functions independently of any app or website already on the web server, working with events listeners and commands such as "fetch", which is similar to the HTTP commands "Get / Post / Set".
As it listens to the network requests on the server, but it is located as a .js file in the user device, the service worker will handle these requests with appropriate responses depending on whether there is an Internet connection or not, allowing customized pages offline.
Once these four requirements have been correctly implemented, users of Android phones and other compatible devices will be asked to add the PWA to their home screen, where there will be an icon similar to a regular app, which will open in a browser.
Who is already using PWA?
Even though Progressive Web Apps build on new technologies, they are already widely in use in the industry. Some of the larger showcases for PWA are:

Great for all, awesome for most

# How I built my first pwa ?
Here I was very much fascinated about pwa's and I started diving into it. Here is my tutorial to built a small effective and impressive webapps. This easy example walks you through building a PWA from scratch to show you all the needed steps and development tools. The example app is a simple news reader that allows you to fetch news from different sources and view them offline. 
Topics covered: Web App Manifest, Service Worker, Chrome DevTools.
https://prodigl.github.io/waffle-news/
Things you should have knowledge about ?
•	Basic Html
•	Basic Css
•	Baisc Javascript 
•	Basic knowledge of Json text
Ps: I have also included some CSS files of a AIONE framework which in turn is also supportable for building pwa's. You can easily customise yourself.

# How your basic html structure should look like ?

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Waffle news</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" type="text/css" href="https://fonts.googleapis.com/css?family=Open+Sans:100,300,400,600,700,800,900">
  <link rel="stylesheet" type="text/css" href="https://aioneframework.com/aioneframework/assets/css/aione.min.css"> 
  <link rel="stylesheet" href="styles.css">
  <link rel="manifest" href="manifest.json">
  <meta name="description" content="A Progressive Web application to access top healdlines from any newspaper of the world.">
  <meta name="keywords" content="Progressive web applicaion, news app, all in one news app">
  <meta name="author" content="Rahul Kumar">
  <meta name="theme-color" content="#ffffff" />
</head>
<body>  <div class="center-align bg-black p-10">
 <h1 class="white">Waffle News</h1>
  </div>
  <div class="p-10 ">
    <label class="line-height-34 bold font-size-20" for="sources">Select Channel</label>
    <select class=""  id="sources"></select>
  </div>
  <div class="p10">
  <main class="p-10"></main>
</div>
  <script src="app.js"></script>
</body>
</html>

## Explanation 
All you see what I have integrated in the html code is 
My style sheet
Called Aione framework libraries in the link tag
Manifest file and
JavaScript file in the body section
You might be confused where is the service worker well as you know it's a script file its been called in the app.js
 
 # My CSS sheet

select{
 
  color: #000000;
  background-color: #ffffff; 
}
select option{
  color: #000000;
  background-color: #ffffff;
}


h2 {
    display: block;
    font-size: 1.5em;
    -webkit-margin-before: 0.83em;
    -webkit-margin-after: 0.83em;
    -webkit-margin-start: 0px;
    -webkit-margin-end: 0px;
    font-weight: 300px;
    color: white;
}
h1 {
  text-transform: uppercase;
  font-weight: 300;
    font-size: 64px;
    line-height: 110%;
    margin: 0px;
    color: white;
}

h5 {
    font-size: 18px;
    line-height: 110%;
    margin: 9px 0 7.2px 0;
    color: white;
}


main {
  display: grid;
  grid-gap: 30px;
  background-color: #444444;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  grid-auto-rows: max-content;
  grid-auto-flow: row dense;
}


.article a,
.article a:visited {
  text-decoration: none;
  color: inherit;
}

.article img {
  width: 100%;
}
## Explaination
You can customise yours accordindly

# Manifest File

{
  "name": "Waffle News",
  "short_name": "Waffle News",
  "theme_color": "#ffffff",
  "background_color": "#ffffff",
  "display": "standalone",
  "Scope": "/",
  "start_url": ".",
  "icons": [
    {
      "src": "images/icons/icon-72x72.png",
      "sizes": "72x72",
      "type": "image/png"
    },
    {
      "src": "images/icons/icon-96x96.png",
      "sizes": "96x96",
      "type": "image/png"
    },
    {
      "src": "images/icons/icon-128x128.png",
      "sizes": "128x128",
      "type": "image/png"
    },
    {
      "src": "images/icons/icon-144x144.png",
      "sizes": "144x144",
      "type": "image/png"
    },
    {
      "src": "images/icons/icon-152x152.png",
      "sizes": "152x152",
      "type": "image/png"
    },
    {
      "src": "images/icons/icon-192x192.png",
      "sizes": "192x192",
      "type": "image/png"
    },
    {
      "src": "images/icons/icon-384x384.png",
      "sizes": "384x384",
      "type": "image/png"
    },
    {
      "src": "images/icons/icon-512x512.png",
      "sizes": "512x512",
      "type": "image/png"
    }
  ],
  "splash_pages": null
}

## Explanation 
As already explained what an manifest file and where you can get it. Manifest file basically consists the information of the logo of your pwa.

# The Service worker

const cacheName = 'news-v1';
const staticAssets = [
  './',
  './app.js',
  './styles.css',
  './fallback.json',
  './images/fetch-dog.jpg'
];
self.addEventListener('install', async function () {
  const cache = await caches.open(cacheName);
  cache.addAll(staticAssets);
});

self.addEventListener('activate', event => {
  event.waitUntil(self.clients.claim());
});

self.addEventListener('fetch', event => {
  const request = event.request;
  const url = new URL(request.url);
  if (url.origin === location.origin) {
    event.respondWith(cacheFirst(request));
  } else {
    event.respondWith(networkFirst(request));
  }
});

async function cacheFirst(request) {
  const cachedResponse = await caches.match(request);
  return cachedResponse || fetch(request);
}

async function networkFirst(request) {
  const dynamicCache = await caches.open('news-dynamic');
  try {
    const networkResponse = await fetch(request);
    dynamicCache.put(request, networkResponse.clone());
    return networkResponse;
  } catch (err) {
    const cachedResponse = await dynamicCache.match(request);
    return cachedResponse || await caches.match('./fallback.json');
  }
}

## Explanation 
As service worker is used to cache the sources you wish, here i have cached my home page of the website and fallback.json file which consist an image which will be shown when your internet connectivity is gone you wish to load the resources of the site.

# And your application JavaScript file

const apiKey = '237bb7c05d1340768e1c826a89ccf823';
const defaultSource = 'the-washington-post';
const sourceSelector = document.querySelector('#sources');
const newsArticles = document.querySelector('main');

if ('serviceWorker' in navigator) {
  window.addEventListener('load', () =>
    navigator.serviceWorker.register('sw.js')
      .then(registration => console.log('Service Worker registered'))
      .catch(err => 'SW registration failed'));
}

window.addEventListener('load', e => {
  sourceSelector.addEventListener('change', evt => updateNews(evt.target.value));
  updateNewsSources().then(() => {
    sourceSelector.value = defaultSource;
    updateNews();
  });
});

window.addEventListener('online', () => updateNews(sourceSelector.value));

async function updateNewsSources() {
  const response = await fetch(`https://newsapi.org/v2/sources?apiKey=${apiKey}`);
  const json = await response.json();
  sourceSelector.innerHTML =
    json.sources
      .map(source => `<option value="${source.id}">${source.name}</option>`)
      .join('\n');
}

async function updateNews(source = defaultSource) {
  newsArticles.innerHTML = '';
  const response = await fetch(`https://newsapi.org/v2/top-headlines?sources=${source}&sortBy=top&apiKey=${apiKey}`);
  const json = await response.json();
  newsArticles.innerHTML =
    json.articles.map(createArticle).join('\n');
}

function createArticle(article) {
  return `
    <div class="article">
      <a href="${article.url}">
        <h2>${article.title}</h2>
        <img src="${article.urlToImage}" alt="${article.title}">
        <h5>${article.description}</h5>
      </a>
    </div>
  `;
}
## Explaination
Don't get panic.
I know it's already lot to digest but this simple code is just nothing has two parts in it :
1. Is registering your service worker to the browser
2. Calling the api for your app from newsapi.org
You can easily understand what's happening in the service worker  section part is that simply following its lifecycle . Start debugging your service worker using your Chrome Dev tool if you wish to dive in.
 https://developers.google.com/web/fundamentals/primers/service-workers/
Calling your news api is way more simple just go to newsapi.org and generate your own api key and you are good to go. 



