<?php
// Insert your keys/tokens

/*
$consumerKey = '8BuXXUgWXFoQPX4FpkT3Pw';
$consumerSecret = '1YEHFXXZ3xtWBDQsIDLVsyJzGgMttO01fxsYbjus';
$oAuthToken = '586447624-bkfw6T7Q2CotShMC9gosKAMoWa7dnIpoBjzGzLGK';
$oAuthSecret = 'AuCpc9BUHZH8rQmsXtYCG3vt0BOgnrgh9FfmMCQQUzo';

*/
$consumerKey = 'U5NABkx6V40pZoMa6vDw';
$consumerSecret = 'pAGSTzix9tvZH79Bcx1wWTl8IVPgSclvPbKWwJ3TLMw';
$oAuthToken = '1518329436-XwINnnxVtDidYIiIDpU8PBq0I9yNI0uPutTIJDP';
$oAuthSecret = 'IDsdVVpmbEEwG11U58sahmPmXid3apoOetHfcUH8og';



/*$db = new mysqli('localhost','superted','supersecure','superted_dev');
$q = $db->query("SELECT * FROM st_twitter LIMIT 1;");
$q = $q->fetch_object();

$consumerKey = 'c0taj9qx1ZNCeH8NxmRITg';
$consumerSecret = 'YcyYWzCPIQJu0dWq5kAsbYc8Fbnxo7fJTO9TtgkPRSU';
$oAuthToken = $q->token;
$oAuthSecret = $q->token_secret;*/

//echo $_SERVER['DOCUMENT_ROOT'].'test_twitter/twitter-oauth/twitteroauth.php'; exit;

// Full path to twitteroauth.php (change oauth to your own path)
require_once($_SERVER['DOCUMENT_ROOT'].'test_twitter/twitter-oauth/twitteroauth.php');

// create new instance
$tweet = new TwitterOAuth($consumerKey, $consumerSecret, $oAuthToken, $oAuthSecret);

// Your Message
$message = "This is a test message.";

// 'statuses/update', array('status' => "$message")
//Send tweet 
$res = $tweet->post('statuses/update', array('status' => "$message"));
print_r($res);
?>
