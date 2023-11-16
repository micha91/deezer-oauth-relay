# deezer-oauth-relay
A small 10 line relay service for the Music Assistant Deezer integration. This is needed because Deezer only allows oauth to specific urls (In this case https://deezer.oauth.jonathanbangert.com/). All it does is it recieves the oauth redirect from deezer and then instantly redirects back to the local music assistant instance. 

This is all the code:
```html
<html>
    <head>
        <script>
            let params = window.location.search.replace('?','').split('&');
            let code = params[0].split('=')[1];
            let server_url = params[1].split('=')[1];
            window.location.replace(server_url + '?code=' + code)
        </script>
    </head>
</html>
```
