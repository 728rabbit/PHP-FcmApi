# googe_firebase_cloud_messaging_api

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
    dump($result);
}   
else {
    echo $FcmApi->getError();
}
