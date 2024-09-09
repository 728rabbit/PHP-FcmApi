# FcmApi
The FcmApi class is a PHP implementation designed to interact with Firebase Cloud Messaging (FCM) for sending push notifications. It uses OAuth 2.0 for authentication and JWT for secure access.

    require app_path('Libraries/FcmApi.php');
    $FcmApi = new \FcmApi(
    [
        'path' => 'your_firebase_adminsdk_json_file', 
        'project_id' => 'your_firebase_project_id'
    ]);
    
    $token = 'your_target_device_token';
    if($result = $FcmApi->setMessage(
    [
        'title' => 'Hi', 
        'body' => 'Hello World!'
    ])->send($token)) {
        echo 'Message sent successfully. Message ID: '. $result['name'];
    }   
    else {
        echo $FcmApi->getError();
    }
