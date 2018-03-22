# React Native fetch() Network Request Failed


When I create a brand new project using react-native init (RN version 0.29.1) and put a fetch in the render method to the public facebook demo movie API, it throws a Network Request Failed. There is a very useless stack trace and I can't debug network requests in the chrome console. Here is the fetch I'm sending:
```

fetch('http://facebook.github.io/react-native/movies.json')
      .then((response) => response.json())
      .then((responseJson) => {
        return responseJson.movies;
      })
      .catch((error) => {
        console.error(error);
      });
```


The problem here was that iOS does not allow http requests by default, only https. If you want to enable http requests add this to your info.plist:

```
<dict>
		<key>NSExceptionDomains</key>
		<dict>
			<key>facebook.github.io</key>
			<dict>
				<key>NSExceptionAllowsInsecureHTTPLoads</key>
				<true/>
			</dict>
		</dict>
	</dict>
```

[React Native fetch() Network Request Failed](https://stackoverflow.com/questions/38418998/react-native-fetch-network-request-failed)