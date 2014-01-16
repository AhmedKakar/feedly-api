feedly-api
==========

PHP wrapper around [Feedly's REST API](http://developer.feedly.com/)

Documentation
---------
Constructor:
```php
    /**
     * @param boolean $sandbox                   Enable/Disable Sandbox Mode
     * @param boolean $storeAccessTokenToSession Choose whether to store the Access token
     *                                           to $_SESSION or not
     */
     
    $feedly = new Feedly($sandbox=FALSE, $storeAccessTokenToSession=TRUE);
```

```php
    /**
     * Return authorization URL
     * @param string $client_id     Client's ID provided by Feedly's Administrators
     * @param string $redirect_uri  Endpoint to reroute with the results
     * @param string $response_type
     * @param string $scope
     *
     * @return string Authorization URL
     */
    $feedly->getLoginUrl($client_id, $redirect_uri,
        $response_type="code", $scope="https://cloud.feedly.com/subscriptions") 
```

```php
    /**
     * Exchange a `code` got from `getLoginUrl` for an `Access Token`
     * @param string $client_id     Client's ID provided by Feedly's Administrators
     * @param string $client_secret Client's Secret provided by Feedly's Administrators
     * @param string $auth_code     Code obtained from `getLoginUrl`
     * @param string $redirect_url  Endpoint to reroute with the results
     */
    $feedly->GetAccessToken($client_id, $client_secret, $auth_code,
        $redirect_url) 
```

[Get The Profile of The User](http://developer.feedly.com/v3/profile/#get-the-profile-of-the-user)
```php
/**
     * @param  string $token Access Token in case we don't store it to $_SESSION
     * @return json   Response from the server
     */
    $feedly->getProfile($token=NULL) 
```

[Get The Preferences of The User](http://developer.feedly.com/v3/preferences/#get-the-preferences-of-the-user)

```php
    /**
     * @param  string $token Access Token in case we don't store it to $_SESSION
     * @return json   Response from the server
     */
    $feedly->getPreferences($token=NULL)
```

[Get The List Of All Categories](http://developer.feedly.com/v3/categories/#get-the-list-of-all-categories)

```php
    /**
     * @param  string $token Access Token in case we don't store it to $_SESSION
     * @return json   Response from the server
     */
    $feedly->getCategories($token=NULL)
```

[Get The Subscriptions of The User](http://developer.feedly.com/v3/subscriptions/#get-the-users-subscriptions)

```php
    /**
     * @param  string $token Access Token in case we don't store it to $_SESSION
     * @return json   Response from the server
     */
    $feedly->getSubscriptions($token=NULL) 
```

[Get The Metadata About a Specific Feed](http://developer.feedly.com/v3/feeds/#get-the-metadata-about-a-specific-feed)

```php
    /**
     * @param  string $feedId Feed's ID
     * @param  string $token Access Token in case we don't store it to $_SESSION
     * @return json   Response from the server
     */
    $feedly->getFeedMetadata($feedId, $token=NULL) 
```

[Get The Content of A Stream](http://developer.feedly.com/v3/streams/#get-the-content-of-a-stream)

```php
    /**
     * @param  string $streamId Stream's ID
     * @param  string $token Access Token in case we don't store it to $_SESSION
     * @return json   Response from the server
     */
    $feedly->getStreamContent($streamId, $count=NULL, $ranked=NULL,
        $unreadOnly=NULL, $newerThan=NULL, $continuation=NULL, $token=NULL) 
```

[Get a mix of the most engaging content available in a stream](http://developer.feedly.com/v3/mixes/#get-a-mix-of-the-most-engaging-content-available-in-a-stream)

```php
    /**
     * @param  string $streamId Stream's ID
     * @param  string $token Access Token in case we don't store it to $_SESSION
     * @return json   Response from the server
     */
    $feedly->getMixes($streamId, $count=NULL, $unreadOnly=NULL,
        $newerThan=NULL, $hours=NULL, $token=NULL) 
```

[Get a List of Entry IDs For a Specific Stream](http://developer.feedly.com/v3/streams/#get-a-list-of-entry-ids-for-a-specific-stream)

```php
    /**
     * @param  string $streamId Stream's ID
     * @param  string $token Access Token in case we don't store it to $_SESSION
     * @return json   Response from the server
     */
    $feedly->getStreamIds($streamId, $count=NULL, $ranked=NULL,
        $unreadOnly=NULL, $newerThan=NULL, $continuation=NULL, $token=NULL) 
```

[Get The List Of Topics The User Has Added To Their Feedly](http://developer.feedly.com/v3/topics/#get-the-list-of-topics-the-user-has-added-to-their-feedly)

```php
    /**
     * @param  string $token Access Token in case we don't store it to $_SESSION
     * @return json   Response from the server
     */
    $feedly->getTopics($token=NULL)
```

[Get The List Of Tags Created By The User.](http://developer.feedly.com/v3/tags/#get-the-list-of-tags-created-by-the-user)

```php
    /**
     * @param  string $token Access Token in case we don't store it to $_SESSION
     * @return json   Response from the server
     */
   $feedly->getTags($token=NULL)
```

[Find Feeds Based On Title, Url Or #topichttp://developer.feedly.com/](http://developer.feedly.com/v3/search/#find-feeds-based-on-title-url-or-topichttpdeveloperfeedlycom)

```php
    /**
     * @param  string $token Access Token in case we don't store it to $_SESSION
     * @return json   Response from the server
     */
    $feedly->searchFeeds($q, $n=NULL, $token=NULL)
```

[Get The List Of Onread Counts](http://developer.feedly.com/v3/markers/#get-the-list-of-unread-counts)

```php
    /**
     * @param  string $token Access Token in case we don't store it to $_SESSION
     * @return json   Response from the server
     */
    $feedly->getUnreadCounts($autorefresh=NULL, $newerThan=NULL,
        $streamId=NULL, $token=NULL)
```

Licence
==================
```
The MIT License (MIT)

Copyright (c) 2014 Konstantinos Bariotis

Permission is hereby granted, free of charge, to any person obtaining a copy of
this software and associated documentation files (the "Software"), to deal in
the Software without restriction, including without limitation the rights to
use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of
the Software, and to permit persons to whom the Software is furnished to do so,
subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS
FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR
COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER
IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN
CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
```
