<?php
class Home extends AppModel {
var $useTable=false;
var $name="Home";
function index()  {

  /* for facebook login */
  require 'includes/src/facebook.php';

   // Create our Application instance (replace this with your appId and secret).
   $facebook = new Facebook(array(
  'appId'  => 'Your App Id',
  'secret' => 'Your App Secret',
   ));

  // Get User ID
  $data['user'] = $facebook->getUser();

  // We may or may not have this data based on whether the user is logged in.
  //
  // If we have a $user id here, it means we know the user is logged into
  // Facebook, but we don't know if the access token is valid. An access
  // token is invalid if the user logged out of Facebook.

  if ($data['user']) {
  try {
    // Proceed knowing you have a logged in user who's authenticated.
     $data['user_profile'] = $facebook->api('/me');
  } catch (FacebookApiException $e) {
    error_log($e);
    $user = null;
  }
  }

  // Login or logout url will be needed depending on current user state.
  if ($data['user']) {
   $data['logout_url'] = $facebook->getLogoutUrl();
   $data['login_url'] = $facebook->getLoginUrl();
  } else {
   $data['login_url'] = $facebook->getLoginUrl();
  }
  /* for facebook login */  

  /* for twitter login */
  $consumerKey = 'Your Consumer key';
  $consumerSecret = 'Your Consumer Secret';
  $oAuthToken = 'Your Auth Token';
  $oAuthSecret = 'Your Auth Secret';


  require 'includes/twitter-oauth/twitteroauth.php';
  
  // create new instance
  $tweet = new TwitterOAuth($consumerKey, $consumerSecret);
 
  $token =$tweet->getAccessToken('Your App Url');

 $_SESSION['oauth_request_token'] = $token['oauth_token'];
 $_SESSION['oauth_request_token_secret'] = $token['oauth_token_secret'];

 
  $request_link = $tweet->getAuthorizeURL($token);
 
  $data['link'] = $request_link;
  /* for twitter login */

  /* for google login */ 
  include('includes/googlesrc/Google_Client.php');
  include('includes/googlesrc/contrib/Google_Oauth2Service.php');


  $client = new Google_Client();
  $client->setApplicationName("Google+ PHP Starter Application");

  // client id, client secret, and to register your redirect uri.
  $client->setClientId('Your Client ID'); 
  $client->setClientSecret('Your Client Secret');
  $client->setRedirectUri('Redirect Url');
  $client->setDeveloperKey('Your Developer key');
  $plus = new Google_Oauth2Service($client);

  $data['authUrl'] = $client->createAuthUrl();
  $data['glogout_url'] = 'Your App Url';
 /* for google login */ 

  return $data; // returns the data to the controller

  }
  
}

?>
