- š Hi, Iām @Srd8
- š Iām interested in ...
- š± Iām currently learning ...
- šļø Iām looking to collaborate on ...
- š« How to reach me ...

<!---
Srd8/Srd8 is a āØ special āØ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
<?php
/*
DEV: @iOm3y
CH : https://t.me/ZEPD8
$API_KEY"5220076610"
*/
ob_start();
$API_KEY = "5170653836:AAFQ3VnTueZghQPTCYCV2lcseqkgNnQZkoE";
define('API_KEY','5170653836:AAFQ3VnTueZghQPTCYCV2lcseqkgNnQZkoE');
define('API_KEY','5170653836:AAFQ3VnTueZghQPTCYCV2lcseqkgNnQZkoE');
echo "https://api.telegram.org/bot".API_KEY."/setwebhook?url=".$_SERVER['SERVER_NAME']."".$_SERVER['SCRIPT_NAME'];
  
define('NO', 'ā');
define('YES', 'ā');
define("API_KEY", $API_KEY);
#                    iSONIC                       #
function bot($method,$datas=[]){
    $url = "https://api.telegram.org/bot".API_KEY."/".$method;
    $ch = curl_init();
    curl_setopt($ch,CURLOPT_URL,$url);
    curl_setopt($ch,CURLOPT_RETURNTRANSFER,true);
    curl_setopt($ch,CURLOPT_POSTFIELDS,$datas);
    $res = curl_exec($ch);
    if(curl_error($ch)){
        var_dump(curl_error($ch));
    }else{
        return json_decode($res);
    }
}
#                     iSONIC                       #
$update = json_decode(file_get_contents('php://input'));
$message = $update->message;
$chat_id = $message->chat->id;
$text = $message->text;
$message_id = $message->message_id;
$reply = $message->reply_to_message;
$user = 'iOm3y'.$message->from->username;
$chat_id2 = $update->callback_query->message->chat->id;
$message_id = $update->callback_query->message->message_id;
$data = $update->callback_query->data;
$get = json_decode(file_get_contents('data.json'),true);
if($user == null){
	$user = $message->from->first_name;
}
$userid = $message->from->id;
$GLOBALS['id'] = $chat_id;
$get = file_get_contents("https://api.telegram.org/bot$API_KEY/getChatMember?chat_id=$chat_id&user_id=".$userid);
$info = json_decode($get, true);
$you = $info['result']['status'];
#                     iSONIC                       #
function lock($media,$type = 'del'){
    $id = $GLOBALS['id'];
    $get = json_decode(file_get_contents('data.json'),true);
    if ($type == 'del') {
        $get[$id][$media]['del'] = NO;
        $get[$id][$media]['ban'] = YES;
        $get[$id][$media]['warn'] = YES;
    }
    if ($type == 'ban') {
        $get[$id][$media]['del'] = YES;
        $get[$id][$media]['ban'] = NO;
        $get[$id][$media]['warn'] = YES;
    }
    if ($type == 'warn') {
        $get[$id][$media]['del'] = YES;
        $get[$id][$media]['ban'] = YES;
        $get[$id][$media]['warn'] = NO;
    }
    file_put_contents('data.json', json_encode($get));
}
function open($media){
    $id = $GLOBALS['id'];
    $get = json_decode(file_get_contents('data.json'),true);
    $get[$id][$media]['del'] = YES;
    $get[$id][$media]['ban'] = YES;
    $get[][$media]['warn'] = YES;
    file_put_contents('data.json', json_encode($get));
}
function check($media){
    $id = $GLOBALS['id'];
    $get = json_decode(file_get_contents('data.json'),true);
    foreach ($get[$id][$media] as $key => $value) {
        if ($get[$id][$media][$key] == NO) {
            return $key;
        }
    }
}
#                    iSONIC                      #

if($text == '/start') {
    bot('sendMessage',[
        'chat_id'=>$chat_id,
        'text'=>"š©ļæ¤Ų§ŁŁŲ§ Ų¹Ų²ŁŲ²Ł :- $name  
āŖļøļæ¤ŁŲ±Ų­ŲØŲ§ ŲØŁ ŁŁ ŲØŁŲŖ Ų§ŁŲ­ŁŲ§ŁŲ©
šļæ¤ŁŁ ŲØŲ§Ų¶Ų§ŁŲŖ Ų§ŁŲØŁŲŖ ŁŲ§Ų±ŁŲ¹Ł Ų§ŲÆŁŁ ŁŲ³ŁŲŖŁ Ų§ŁŲŖŁŲ¹ŁŁ :) š¤
-ā­",
'reply_to_message_id'=>$mid,
    'reply_markup'=>json_encode([
      'inline_keyboard'=>[
        [['text'=>"Ų§Ų¶ŁŁŁ Ų§ŁŁ Ų§ŁŁŲ¬ŁŁŲ¹Ł š®š¶āļø",'url'=>"t.me/?startgroup=new"]],
        [['text'=>"~ ŲŖŲ§ŲØŲ¹ š®š¶-āļø", 'url'=>"t.me/https://t.me/ZEPD8"]]
    ]

  ])
  ]);
}
// ŲØŲÆŲ§ŁŁ Ų§ŁŁŁŁ ŁŲ§ŁŁŲŖŲ­
if ($you == "creator" or $you == "administrator") {
    if($text == 'ŲŖŁŲ¹ŁŁ Ų§ŁŲŖŲ±Ų­ŁŲØ'){
    		
    	 bot('sendmessage',[
              'chat_id'=>$chat_id,                   'text'=>" ā¢ ŲŖŁ ŲŖŁŲ¹ŁŁ Ų§ŁŲŖŲ±Ų­ŁŲØ - ā
- Ų§ŁŲŖŲ±Ų­ŁŲØ Ų§ŁŲ­Ų§ŁŁ : ".$get[$chat_id]['wel']
                    ]);
                    $get[$chat_id]['_wel'] = true; 	file_put_contents('data.json',json_encode($get));
    }
    if($text == 'ŲŖŲ¹Ų·ŁŁ Ų§ŁŲŖŲ±Ų­ŁŲØ'){
    		
    	 bot('sendmessage',[
              'chat_id'=>$chat_id,                   'text'=>" ā¢ ŲŖŁ ŲŖŲ¹Ų·ŁŁ Ų§ŁŲŖŲ±Ų­ŁŲØ - ".NO."
- Ų§ŁŲŖŲ±Ų­ŁŲØ Ų§ŁŲ­Ų§ŁŁ : ".$get[$chat_id]['wel']
                    ]);
                    $get[$chat_id]['_wel'] = false; 	file_put_contents('data.json',json_encode($get));
    }
    if($reply and $text == 'Ų·Ų±ŲÆ' or $text == 'Ų­ŲøŲ±'){
	bot('kickchatmember',[
		'chat_id'=>$chat_id,
		'user_id'=>$reply->from->id
	]);
	bot('sendMessage',[
		'chat_id'=>$chat_id,
		'text'=>"
    Ų§ŁŲ¹Ų¶Ł : š®š¶-āļø  āć   @".$reply->from->username."  ć
 { < š®š¶ ŲŖŁ Ų§ŁŲ­ŲøŲ± š®š¶ > } 

    ",
		'reply_markup'=>json_encode([
		'inline_keyboard'=>[
		
		]
		])
	]);
}
  
    if($reply and $text == 'Ų·Ų±ŲÆ' or $text == 'Ų­ŲøŲ±'){
	bot('unbanchatmember',[
		'chat_id'=>$chat_id2,
		'user_id'=>$data
	]);
	bot('editmessagetext',[
		'chat_id'=>$chat_id2,
		'text'=>"
Ų§ŁŲ¹Ų¶Ł : š®š¶-āļø  āć   @".$reply->from->username."  ć
 { < š®š¶ ŲŖŁ Ų§ŁŲŗŲ§Ų” Ų­ŲøŲ± š®š¶ > } 

    ",
		'reply_markup'=>json_encode([
		'inline_keyboard'=>[
		
		]
		])
	]);
}
  
if($reply and $text == 'ŲŖŲ«ŲØŁŲŖ'){
	bot('pinchatmessage',[
		'chat_id'=>$chat_id,
		'message_id'=>$reply->message_id
	]);
}
if($reply and $text == 'Ų§ŁŲŗŲ§Ų” Ų§ŁŲŖŲ«ŲØŁŲŖ'){
	bot('unpinchatmessage',[
		'chat_id'=>$chat_id,
		'message_id'=>$reply->message_id
	]);
}
if(preg_match('/Ų¶Ų¹ Ų§Ų³Ł .*/',$text)){
	$text = str_replace('Ų¶Ų¹ Ų§Ų³Ł ','',$text);
	bot('setchattitle',[
		'chat_id'=>$chat_id,
		'title'=>$text
	]);
}



    if (preg_match('/(ŁŁŁ)(.*)(.*)/', $text)) {
        $text = trim(str_replace('ŁŁŁ', '', $text));
        $text = explode(' ', $text);
        if (isset($text[0])) {
            if ($text[0] == 'Ų§ŁŲµŁŲ±' or $text[0] == 'Ų§ŁŁŁŲÆŁŁ' or $text[0] == 'Ų§ŁŲØŲµŁŲ§ŲŖ' or $text[0] == 'Ų§ŁŲµŁŲŖ' or $text[0] == 'Ų§ŁŁŲŖŲ­Ų±ŁŁ' or $text[0] == 'Ų§ŁŲ±ŁŲ§ŲØŲ·' or $text[0] == 'Ų§ŁŲ¬ŁŲ§ŲŖ' or $text[0] == 'Ų§ŁŁŁŁŲ§ŲŖ' or $text[0] == 'Ų§ŁŁŲ§Ų±ŁŲÆŁŁ' or $text[0] == 'Ų§ŁŲŖŁŲ¬ŁŁ' or $text[0] == 'Ų§ŁŲØŁŲŖŲ§ŲŖ' or $text[0] == 'Ų§ŁŁŁŲµŁŲ§ŲŖ' or $text[0] == 'Ų§ŁŁŲ¹Ų±Ł' or $text[0] == 'Ų§ŁŲØŁŲŖŲ§ŲŖ' and $text[1] == 'ŲØŲ§ŁŲ­Ų°Ł' or $text[1] == 'ŲØŲ§ŁŲ·Ų±ŲÆ' or $text[1] == 'ŲØŲ§ŁŲŖŲ­Ų°ŁŲ±'){
                switch ($text[0]) {
                    case 'Ų§ŁŲµŁŲ±':$m = 'photo';break;
                    case 'Ų§ŁŁŁŲÆŁŁ':$m = 'video';break;
                    case 'Ų§ŁŲØŲµŁŲ§ŲŖ':$m = 'voice';break;
                    case 'Ų§ŁŲµŁŲŖ':$m = 'audio';break;
                    case 'Ų§ŁŁŲŖŲ­Ų±ŁŁ':$m = 'gif';break;
                    case 'Ų§ŁŲ±ŁŲ§ŲØŲ·':$m = 'link';break;
                    case 'Ų§ŁŲ¬ŁŲ§ŲŖ':$m = 'contact';break;
                    case 'Ų§ŁŁŁŁŲ§ŲŖ':$m = 'doc';break;
                    case 'Ų§ŁŁŲ§Ų±ŁŲÆŁŁ':$m = 'mark';break;
                    case 'Ų§ŁŲŖŁŲ¬ŁŁ':$m = 'fwd';break;
                    case 'Ų§ŁŁŁŲµŁŲ§ŲŖ':$m = 'sticker';break;
                    case 'Ų§ŁŁŲ¹Ų±Ł':$m = 'user';break;
                    case 'Ų§ŁŲØŁŲŖŲ§ŲŖ':$m='bots';break;
                           if($text[1] == null){
              	$text[1] = 'ŲØŲ§ŁŲ­Ų°Ł';
              }
                }
                switch ($text[1]) {
                    case 'ŲØŲ§ŁŲ­Ų°Ł':$t='del';break;
                    case 'ŲØŲ§ŁŲ·Ų±ŲÆ':$t='ban';break;
                    case 'ŲØŲ§ŁŲŖŲ­Ų°ŁŲ±':$t='warn';break;
                    default:
                        $t='del';
                        break;
                }
      
                lock($m,$t);
                bot('sendmessage',[
                    'chat_id'=>$chat_id,
                    'text'=>"
                    Ł ŲŖŁŁŁ ŁŁŁŁŁ š āć $text[0]  ć
 { < š®š¶ Ų®Ų§ŲµŁŲ© : $text[1] š®š¶ > } 
                    "
                ]);
            }
        }
    }
    #                     ISONIC                       #
    if (preg_match('/(ŁŲŖŲ­)(.*)(.*)/', $text)) {
        $text = trim(str_replace('ŁŲŖŲ­', '', $text));
        $text = explode(' ', $text);
        if (isset($text[0])) {
            if ($text[0] == 'Ų§ŁŲµŁŲ±' or $text[0] == 'Ų§ŁŁŁŲÆŁŁ' or $text[0] == 'Ų§ŁŲØŲµŁŲ§ŲŖ' or $text[0] == 'Ų§ŁŲµŁŲŖ' or $text[0] == 'Ų§ŁŁŲŖŲ­Ų±ŁŁ' or $text[0] == 'Ų§ŁŲ±ŁŲ§ŲØŲ·' or $text[0] == 'Ų§ŁŲ¬ŁŲ§ŲŖ' or $text[0] == 'Ų§ŁŁŁŁŲ§ŲŖ' or $text[0] == 'Ų§ŁŁŲ§Ų±ŁŲÆŁŁ' or $text[0] == 'Ų§ŁŲŖŁŲ¬ŁŁ' or $text[0] == 'Ų§ŁŁŁŲµŁŲ§ŲŖ' or $text[0] == 'Ų§ŁŁŲ¹Ų±Ł' or $text[0] == 'Ų§ŁŲØŁŲŖŲ§ŲŖ'){
                switch ($text[0]) {
                    case 'Ų§ŁŲµŁŲ±':$m = 'photo';break;
                    case 'Ų§ŁŁŁŲÆŁŁ':$m = 'video';break;
                    case 'Ų§ŁŲØŲµŁŲ§ŲŖ':$m = 'voice';break;
                    case 'Ų§ŁŲµŁŲŖ':$m = 'audio';break;
                    case 'Ų§ŁŁŲŖŲ­Ų±ŁŁ':$m = 'gif';break;
                    case 'Ų§ŁŲ±ŁŲ§ŲØŲ·':$m = 'link';break;
                    case 'Ų§ŁŲ¬ŁŲ§ŲŖ':$m = 'contact';break;
                    case 'Ų§ŁŁŁŁŲ§ŲŖ':$m = 'doc';break;
                    case 'Ų§ŁŁŲ§Ų±ŁŲÆŁŁ':$m = 'mark';break;
                    case 'Ų§ŁŲŖŁŲ¬ŁŁ':$m = 'fwd';break;
                    case 'Ų§ŁŁŁŲµŁŲ§ŲŖ':$m = 'sticker';break;
                    case 'Ų§ŁŁŲ¹Ų±Ł':$m = 'user';break;
                    case 'Ų§ŁŲØŁŲŖŲ§ŲŖ':$m='bots';break;
                }
                open($m);
               switch(check($m)){
               	case 'del':$t='ŲØŲ§ŁŲ­Ų°Ł';
               	case 'warn':$t='ŲØŲ§ŁŲŖŲ­Ų°ŁŲ±';
               	case 'ban':$t='ŲØŲ§ŁŲ·Ų±ŲÆ';
               	default:$t='ŲØŲ§ŁŲ­Ų°Ł';
               } bot('sendmessage',[
                    'chat_id'=>$chat_id,
                    'text'=>"
                    ŲŖŁ ŁŲŖŲ­ š®š¶-āļø  āć $text[0]  ć
 { < š®š¶ Ų®Ų§ŲµŁŲ© : $t š®š¶ > } 
                    "
                ]);
            }
        }
    }
    
}
// ŁŁŲ§ŁŁ Ų§ŁŁŁŁ ŁŲ§ŁŁŲŖŲ­
if ($you != "creator" and $you != "administrator") {
    if($message->photo){    #                     ISONIC                       #
        if (check('photo') == 'ban') {
            bot('kickChatMember',[
                'chat_id'=>$chat_id,
                'user_id'=>$message->from->id
            ]);
            bot('deleteMessage',[
                'chat_id'=>$chat_id,
                'message_id'=>$message->message_id
            ]);
        }
        if (check('photo') == 'warn') {
            bot('sendmessage',[
                'chat_id'=>$chat_id,
                'text'=>"ā¢ ŁŁŁŁŲ¹ Ų§Ų±Ų³Ų§Ł Ų§ŁŲµŁŲ± #:  ".$user." - ".NO
            ]);
            bot('deleteMessage',[
                'chat_id'=>$chat_id,
                'message_id'=>$message->message_id
            ]);
        }
        if (check('photo') == 'del') {
            bot('deleteMessage',[
                'chat_id'=>$chat_id,
                'message_id'=>$message->message_id
            ]);
        }
    }
    if($message->video){
        if (check('video') == 'ban') {
            bot('kickChatMember',[
                'chat_id'=>$chat_id,
                'user_id'=>$message->from->id
            ]);
            bot('deleteMessage',[
                'chat_id'=>$chat_id,
                'message_id'=>$message->message_id
            ]);
        }
        if (check('video') == 'warn') {
            bot('sendmessage',[
                'chat_id'=>$chat_id,
                'text'=> "ā¢ ŁŁŁŁŲ¹ Ų§Ų±Ų³Ų§Ł ŁŁŲÆŁŁ #:  ".$user." - ".NO
            ]);
            bot('deleteMessage',[
                'chat_id'=>$chat_id,
                'message_id'=>$message->message_id
            ]);
        }
        if (check('video') == 'del') {
            bot('deleteMessage',[
                'chat_id'=>$chat_id,
                'message_id'=>$message->message_id
            ]);
        }
    }
    if($message->contact){
        if (check('contact') == 'ban') {
            bot('kickChatMember',[
                'chat_id'=>$chat_id,
                'user_id'=>$message->from->id
            ]);
            bot('deleteMessage',[
                'chat_id'=>$chat_id,
                'message_id'=>$message->message_id
            ]);
        }
        if (check('contact') == 'warn') {
            bot('sendmessage',[
                'chat_id'=>$chat_id,
                'text'=> "ā¢ ŁŁŁŁŲ¹ Ų§Ų±Ų³Ų§Ł Ų§ŁŲ¬ŁŲ§ŲŖ #:  ".$user." - ".NO
            ]);
            bot('deleteMessage',[
                'chat_id'=>$chat_id,
                'message_id'=>$message->message_id
            ]);
        }
        if (check('contact') == 'del') {
            bot('deleteMessage',[
                'chat_id'=>$chat_id,
                'message_id'=>$message->message_id
            ]);
        }
    }
    if($message->sticker){
        if (check('sticker') == 'ban') {
            bot('kickChatMember',[
                'chat_id'=>$chat_id,
                'user_id'=>$message->from->id
            ]);
            bot('deleteMessage',[
                'chat_id'=>$chat_id,
                'message_id'=>$message->message_id
            ]);
        }
        if (check('sticker') == 'warn') {
            bot('sendmessage',[
                'chat_id'=>$chat_id,
                'text'=> "ā¢ ŁŁŁŁŲ¹ Ų§Ų±Ų³Ų§Ł Ų§ŁŁŁŲµŁŲ§ŲŖ #:  ".$user." - ".NO
            ]);
            bot('deleteMessage',[
                'chat_id'=>$chat_id,
                'message_id'=>$message->message_id
            ]);
        }
        if (check('sticker') == 'del') {
            bot('deleteMessage',[
                'chat_id'=>$chat_id,
                'message_id'=>$message->message_id
            ]);
        }
    }
    if($message->forward_from or $message->forward_from_chat){
        if (check('fwd') == 'ban') {
            bot('kickChatMember',[
                'chat_id'=>$chat_id,
                'user_id'=>$message->from->id
            ]);
            bot('deleteMessage',[
                'chat_id'=>$chat_id,
                'message_id'=>$message->message_id
            ]);
        }
        if (check('fwd') == 'warn') {
            bot('sendmessage',[
                'chat_id'=>$chat_id,
                'text'=> "ā¢ ŁŁŁŁŲ¹ Ų§Ų±Ų³Ų§Ł Ų§ŁŲŖŁŲ¬ŁŁ #:  ".$user." - ".NO
            ]);
            bot('deleteMessage',[
                'chat_id'=>$chat_id,
                'message_id'=>$message->message_id
            ]);
        }
        if (check('fwd') == 'del') {
            bot('deleteMessage',[
                'chat_id'=>$chat_id,
                'message_id'=>$message->message_id
            ]);
        }
    }
    if($message->document){
        if (check('doc') == 'ban') {
            bot('kickChatMember',[
                'chat_id'=>$chat_id,
                'user_id'=>$message->from->id
            ]);
            bot('deleteMessage',[
                'chat_id'=>$chat_id,
                'message_id'=>$message->message_id
            ]);
        }
        if (check('doc') == 'warn') {
            bot('sendmessage',[
                'chat_id'=>$chat_id,
                'text'=> "ā¢ ŁŁŁŁŲ¹ Ų§Ų±Ų³Ų§Ł Ų§ŁŁŁŁŲ§ŲŖ #:  ".$user." - ".NO
            ]);
            bot('deleteMessage',[
                'chat_id'=>$chat_id,
                'message_id'=>$message->message_id
            ]);
        }
        if (check('doc') == 'del') {
            bot('deleteMessage',[
                'chat_id'=>$chat_id,
                'message_id'=>$message->message_id
            ]);
        }
    }
    if(preg_match('/^(.*)([Hh]ttp|[Hh]ttps|t.me)(.*)|([Hh]ttp|[Hh]ttps|t.me)(.*)|(.*)([Hh]ttp|[Hh]ttps|t.me)|(.*)[Tt]elegram.me(.*)|[Tt]elegram.me(.*)|(.*)[Tt]elegram.me|(.*)[Tt].me(.*)|[Tt].me(.*)|(.*)[Tt].me|(.*)telesco.me|telesco.me(.*)/i',$text)){
        if (check('link') == 'ban') {
            bot('kickChatMember',[
                'chat_id'=>$chat_id,
                'user_id'=>$message->from->id
            ]);
            bot('deleteMessage',[
                'chat_id'=>$chat_id,
                'message_id'=>$message->message_id
            ]);
        }
        if (check('link') == 'warn') {
            bot('sendmessage',[
                'chat_id'=>$chat_id,
                'text'=> "ā¢ ŁŁŁŁŲ¹ Ų§Ų±Ų³Ų§Ł Ų§ŁŲ±ŁŲ§ŲØŲ· #:  ".$user." - ".NO
            ]);
            bot('deleteMessage',[
                'chat_id'=>$chat_id,
                'message_id'=>$message->message_id
            ]);
        }
        if (check('link') == 'del') {
            bot('deleteMessage',[
                'chat_id'=>$chat_id,
                'message_id'=>$message->message_id
            ]);
        }
    }
    if($message->new_chat_member->is_bot == true){
        if (check('bots') == 'ban') {
            bot('kickChatMember',[
                'chat_id'=>$chat_id,
                'user_id'=>$ $message->new_chat_member->id
            ]);
            bot('deleteMessage',[
                'chat_id'=>$chat_id,
                'message_id'=>$message->message_id
            ]);
        }
        if (check('bots') == 'warn') {
            bot('sendmessage',[
                'chat_id'=>$chat_id,
                'text'=> "ā¢ ŁŁŁŁŲ¹ Ų§Ų¶Ų§ŁŁ Ų§ŁŲØŁŲŖŲ§ŲŖ #:  ".$user." - ".NO
            ]);
            bot('kickChatMember',[
                'chat_id'=>$chat_id,
                'user_id'=>$ $message->new_chat_member->id
                ]);
        }
        if (check('bots') == 'del') {
            bot('kickChatMember',[
                'chat_id'=>$chat_id,
                'user_id'=>$ $message->new_chat_member->id
                ]);
        }
    }
    if($message->entities){
        if (check('mark') == 'ban') {
            bot('kickChatMember',[
                'chat_id'=>$chat_id,
                'user_id'=>$message->from->id
            ]);
            bot('deleteMessage',[
                'chat_id'=>$chat_id,
                'message_id'=>$message->message_id
            ]);
        }
        if (check('mark') == 'warn') {
            bot('sendmessage',[
                'chat_id'=>$chat_id,
                'text'=> "ā¢ ŁŁŁŁŲ¹ Ų§Ų±Ų³Ų§Ł Ų§ŁŁŲ§Ų±ŁŲÆŁŲ§Ł #:  ".$user." - ".NO
            ]);
            bot('deleteMessage',[
                'chat_id'=>$chat_id,
                'message_id'=>$message->message_id
            ]);
        }
        if (check('mark') == 'del') {
            bot('deleteMessage',[
                'chat_id'=>$chat_id,
                'message_id'=>$message->message_id
            ]);
        }
    }
    if(preg_match('/^(.*) | (.*)|(.*) (.*)|(.*)#(.*)|#(.*)|(.*)#/',$text)){
        if (check('user') == 'ban') {
            bot('kickChatMember',[
                'chat_id'=>$chat_id,
                'user_id'=>$message->from->id
            ]);
            bot('deleteMessage',[
                'chat_id'=>$chat_id,
                'message_id'=>$message->message_id
            ]);
        }
        if (check('user') == 'warn') {
            bot('sendmessage',[
                'chat_id'=>$chat_id,
                'text'=> "ā¢ ŁŁŁŁŲ¹ Ų§Ų±Ų³Ų§Ł Ų§ŁŁŲ¹Ų±ŁŲ§ŲŖ #:  ".$user." - ".NO
            ]);
            bot('deleteMessage',[
                'chat_id'=>$chat_id,
                'message_id'=>$message->message_id
            ]);
        }
        if (check('user') == 'del') {
            bot('deleteMessage',[
                'chat_id'=>$chat_id,
                'message_id'=>$message->message_id
            ]);
        }
    }
    if($message->voice){
        if (check('voice') == 'ban') {
            bot('kickChatMember',[
                'chat_id'=>$chat_id,
                'user_id'=>$message->from->id
            ]);
        }
            bot('deleteMessage',[
                'cthat_id'=>$chat_id,
                'message_id'=>$message->message_id
            ]);
        }
        if (check('voice') == 'warn') {
            bot('sendmessage',[
                'chat_id'=>$chat_id,
                'text'=> "ā¢ ŁŁŁŁŲ¹ Ų§Ų±Ų³Ų§Ł Ų§ŁŲØŲµŁŲ§ŲŖ #:  ".$user." - ".NO
            ]);
            bot('deleteMessage',[
                'chat_id'=>$chat_id,
                'message_id'=>$message->message_id
            ]);
        }
        if (check('voice') == 'del') {
            bot('deleteMessage',[
                'chat_id'=>$chat_id,
                'message_id'=>$message->message_id
            ]);
        }
    }
    if($message->audio){
        if (check('audio') == 'ban') {
            bot('kickChatMember',[
                'chat_id'=>$chat_id,
                'user_id'=>$message->from->id
            ]);
        
        }
            bot('deleteMessage',[
                'chat_id'=>$chat_id,
                'message_id'=>$message->message_id
            ]);
        }
        if (check('audio') == 'warn') {
            bot('sendmessage',[
                'chat_id'=>$chat_id,
                'text'=> "ā¢ ŁŁŁŁŲ¹ Ų§Ų±Ų³Ų§Ł Ų§ŁŲµŁŲŖŁŲ§ŲŖ #:  ".$user." - ".NO
            ]);
            bot('deleteMessage',[
                'chat_id'=>$chat_id,
                'message_id'=>$message->message_id
            ]);
        }
        if (check('audio') == 'del') {
            bot('deleteMessage',[
                'chat_id'=>$chat_id,
                'message_id'=>$message->message_id
            ]);

}


if (preg_match("/\/bc .*/", $text) and $chat_id == 175279237) {
            $f = explode("\n", file_get_contents("users.txt"));
            $text = str_replace("/bc ", "", $text);
            for ($i=0; $i < count($f); $i++) { 
                bot("sendMessage",[
                    "chat_id"=>$f[$i],
                    "text"=>$text
                ]);
            }
        }
        $f = explode("\n", file_get_contents("users.txt"));
        if ($update and !in_array($chat_id, $f)) {
            file_put_contents("users.txt", $chat_id."\n",FILE_APPEND);
        } 
        if ($text == "Ų§ŁŁŲ¬ŁŁŲ¹Ų§ŲŖ" or $text == "/us" and $chat_id == 462603768) {
            bot("sendMessage",[
                "chat_id"=>$chat_id,
                "text"=>count($f)
            ]);
        }

    $info = json_decode(file_get_contents("https://api.telegram.org/bot".API_KEY."/getChatMember?chat_id=@m_k236&user_id=".$chat_id));
$per = $info->result->status;
if ($per == 'left') {
  bot('sendMessage',[
    'chat_id'=>$chat_id,
    'text'=>@iOm3y
  ]);
}


$update = json_decode(file_get_contents('php://input'));
$message = $update->message;
$text = $message->text;
$chat_id =$message->chat->id;
$time = time() + (979 * 11 + 1 + 30);
$ex = explode('ŁŁŁ',$text);
$sudo = 175279237;
$id_sudo = 175279237;
$id = $message->from->id; 
$getid = file_get_contents('ied.txt');
$exid = explode("\n", $getid);
$count = count($exid);
$sudo = 175279237;
$bc = explode("/bc", $text);
$user = $update->message->from->username;
$name = $update->message->from->first_name;
$last_name = $update->message->from->last_name;
$from_id = $update->message->from->id;
$message_id = $update->message->message_id;
$user_id = $update->message->from->user_id;
$sudo = 175279237;
$user_id = $message->from->id;
$name = $message->from->first_name;
$username = $message->from->username;

$sudo = 175279237;
$get = explode("\n", file_get_contents('memberbot.txt'));

$sudo == 175279237;
if($text == "Ų±ŁŲ¹ ŁŲ·Ł ŁŁŁŲ²" and $id == $sudo){
bot('sendMessage',[
'chat_id'=>$chat_id,
'text'=>"Ų§ŁŲ¹Ų¶Ł ŲŖŁ Ų±ŁŲ¹Ł ŁŲ·Ł ŁŁŁŲ² ŲØŁŲ¬Ų§Ų­š¹ā",
'reply_to_message_id'=>$message_id
]);
}
if($text == "Ų±ŁŲ¹ ŁŲ·Ł ŁŁŁŲ²" and $id != $sudo){
bot('sendMessage',[
'chat_id'=>$chat_id,
'text'=>"Ų§ŁŲŖ ŁŁŲ³ ŁŲ·ŁŲ±āļø
šŲ§Ų³ŁŁ:- $name
š³Ų§ŁŲÆŁŁ:- $from_id",
'reply_to_message_id'=>$message_id
]);
}

if($text == '/start' and !in_array($chat_id, $get)){
file_put_contents('users.txt',"\n" . $chat_id, FILE_APPEND);
}

if($text == '/start' and !in_array($chat_id, $get)){
file_put_contents('memberbot.txt',"\n" . $chat_id, FILE_APPEND);
}

if($text == 'ŲØŁŲŖŁ' and $id == $sudo){
bot('sendmessage',[
chat_id=>$chat_id,
'text'=>"ŁŁŁŁŁŁŁŁŁŁŁŁŁŁŲ§Ł ŁŁŁŁŁŁŁŁŁŁŁŁŲ·ŁŁŁŁŁŁŁŁŁŁŁŁŲ±Ł"
]);
}

if($text == 'ŲŖŁŲ¹ŁŁ' ){
bot('sendmessage',[
chat_id=>$chat_id,
'text'=>"š®š¶-āļø ŲŖŁ ŲŖŁŲ¹ŁŁ Ų§ŁŲØŁŲŖ ŲØŁŲ¬Ų§Ų­ 

šŲ§Ų³ŁŁ:- $name 
š³Ų§ŁŲÆŁŁ:- $from_id"
]);
}

  $rep = $message->reply_to_message;
if(preg_match('/^(ŲŖŲ§Ł)(.*)/',$text)){
 $text = str_replace('ŲŖŲ§Ł ŁŁŁŲ·Ł  ','',$text);
 bot('sendmessage',[
 'chat_id'=>$chat_id,
 'text'=>"[$text](tg://user?id=".$rep->from->id.")",
 'parse_mode'=>'markdown'
 ]);
}


if($text == 'ŲØŁŁŲŖŁ' and !$id == $sudo){
bot('sendmessage',[
chat_id=>$chat_id,
'text'=>"ŁŁ ŁŲ·ŁŲ±Ł Ų­Ų³ŲØŲ§ŁŁ ŁŲ§ Ų¹Ų±ŁŁ"
]);
}

if($text == "Ł3"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"āļø- Ų§ŁŁŲ§ ŲØŁŁ Ų¹Ų²ŁŲ²Ł $name ŁŁ ŁŲ§Ų¦ŁŲ© Ų§ŁŁŲÆŁŲ±š¹ 
āāāāāāāāāāā
šŁŲ¹ŁŁŁŲ§ŲŖŁ ā­ ŁŲ¹Ų±Ų¶ ŁŲ¹ŁŁŁŲ§ŲŖŁ Ų§ŁŲ“Ų®ŲµŁŁ

š- Ų§ŁŲÆŁ ŁŁŲ±ŁŲØ ā­ ŁŲ¹Ų±Ų¶ Ų§ŁŲÆŁ ŁŁŲ±ŁŲØ

š- ŁŁŁ+Ų§ŁŁŁŁŁ

šŲ§Ų¶Ł+ŁŁŁŲ© ā­ ŁŲ§Ų¶Ų§ŁŲ© Ų±ŲÆ Ų¹Ų§Ł
Ų¬ŁŲ§ŲØ Ų§ŁŲ±ŲÆ

š- Ų§Ų³ŁŁ ā­ ŁŲ¹Ų±Ų¶ Ų§Ų³ŁŁ
āāāāāāāāāāā
"ŁŲ·ŁŲ± Ų§ŁŲØŁŲŖ @iOm3y"
",
'reply_to_message_id'=>$message->message_id, 
]);
}

if($rep && $text == "Ų§ŁŲÆŁ"){
bot('sendmessage', [
'chat_id' => $chat_id,
'text' => "id = $re_id
name = $re_name
user = $re_user",
]);
}

include 'rd.php';
if (preg_match('/^(Ų§Ų¶Ł)(.*)/', $text) ) {
  $rd = str_replace('Ų§Ų¶Ł ', $rd, $text);
  $ex = explode("\n", $rd);

    $put = "\n".'
    if ($text == "'.$ex[0].'") {
      bot(\'sendMessage\',[
        \'chat_id\'=>$chat_id,
        \'text\'=>"'.$ex[1].'"
      ]);
    }';
    file_put_contents('rd.php', $put,FILE_APPEND);
    bot('sendMessage',[
                'chat_id'=>$chat_id,
                'text'=>"ŲŖŁŁŁ Ų§Ų¶ŁŁŲ§ŁŁŁŲ© Ų§ŁŁŲ±ŲÆ ŲØŁŁŁŲ¬ŁŲ§Ų­ā
ŲØŁŁŲ§Ų³ŁŲ·ŁŁ $name",
'reply_to_message_id'=> $message_id,
                ]);
  
}

if($text== 'Ų§ŁŲ§ŁŲ§ŁŲ±'){
bot('sendMessage',[
"chat_id"=>$chat_id,
'text'=>'Ų§ŁŁŲ§ ŲØŁ Ų¹Ų²ŁŲ²Ł ŁŁ ŁŲ§Ų¦ŁŲ© Ų§ŁŲ§ŁŲ§ŁŲ±

ć°ć°ć°ć°ć°ć°ć°ć°
āļøŲ§ŁŲ§ŁŲ± ŲØŁŲŖ Ų§ŁŲ­ŁŲ§ŁŁ
 
šŲ§ŁŲ§ŁŲ± Ų§ŁŲ­ŁŲ§ŁŁš¹  Ł1

š Ų§ŁŲ§ŁŲ± Ų§ŁŁŁŲ“Ų¦ &Ų§ŁŲ§ŲÆŁŁš¹ Ł 2

šŲ§ŁŲ§ŁŲ± Ų§Ų¶Ų§ŁŁŁš¹  Ł3

āāšŲ§ŁŲ§ŁŲ± Ų§ŁŲ§ŲŗŲ§ŁŁš¹ Ł4
āāāāāā
  
]);
}

if($text=="Ų§Ų³ŁŁ"){
bot('sendmessage',[
'chat_id' => $chat_id,
'text'=>$name
]);
}
if($text == "Ł1"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"š Ų§ŁŁŁ Ų§ŁŲ§ŁŲ± Ų­ŁŲ§ŁŲ© Ų§ŁŁŲ¬ŁŁŲ¹Ł 
ć°ć°ć°ć°ć°ć°ć°ć°ć°ć°ć°
š¹ Ų§Ų³ŲŖŲ®ŲÆŁ Ų§ŁŲ± ( ŁŁŁ ) ŁŁŁŁŁ šā¢
š¹ Ų§Ų³ŲŖŲ®ŲÆŁ Ų§ŁŲ± ( ŁŲŖŲ­ ) ŁŁŁŲŖŲ­ šā¢

šŲ§ŁŁŁ Ų§ŁŲ§ŁŲ§ŁŲ± Ų§ŁŲ­ŁŲ§ŁŁ Ų§ŁŁŲŖŁŁŲ±Ł -
āāāāāāāāāāā
š- Ų§ŁŲµŁŲ± ā¢ š·

š- Ų§ŁŁŁŲÆŁŁ ā¢ š¹

š- Ų§ŁŁŁŲµŁŲ§ŲŖ ā¢ š

š- Ų§ŁŲ±ŁŲ§ŲØŲ· ā¢ š
ļø
š- Ų§ŁŲŖŁŲ¬ŁŁ ā¢ š

š- Ų§ŁŲ¬ŁŲ§ŲŖ ā¢ š„

š- Ų§ŁŁŲ¹Ų±Ł ā¢ #ā£

š-  Ų§ŁŁŲŖŲ­Ų±ŁŁ ā¢ š

š- Ų§ŁŁŁŁŲ§ŲŖ  ā¢ š

š- Ų§ŁŲØŁŲŖŲ§ŲŖ š¤š¾

š- Ų§ŁŲµŁŲŖ ā¢ š¶
ļø
š- Ų§ŁŲØŲµŁŲ§ŲŖ š Ų 

āļø- ŁŁ Ų§ŁŲ§ŁŲ§ŁŲ± ŲŖŲ¹ŁŁ ŁŲ¹ ( ŲØŲ§ŁŲ­Ų°Ł Ų ŲØŲ§ŁŲ·Ų±ŲÆ Ų ŲØŲ§ŁŲŖŲ­Ų°ŁŲ± ) Ų š±
ŁŲ«Ł : ŁŁŁ Ų§ŁŲ±ŁŲ§ŲØŲ· ŲØŲ§ŁŲ·Ų±ŲÆ 
āāāāāāāāāāā 
"ŁŲ·ŁŲ± Ų§ŁŲØŁŲŖ @iOm3y"
",
'reply_to_message_id'=>$message->message_id, 
]);
}
if($text == "Ł2"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"āļøā¢ Ų§ŁŁŁ Ų§ŁŲ§ŁŲ§ŁŲ± Ų§ŁŲ§Ų¶Ų§ŁŁŁ āØ 
āāāāāāāāāāā
š- ŁŲ°Ł Ų§ŁŲ§ŁŲ§ŁŲ± ŁŲŖŲ§Ų­Ł ŁŁŲ§ŲÆŁŁ ŁŲ§ŁŁŁŲ“Ų¦ š¹

š- Ų·Ų±ŲÆ ( ŲØŲ§ŁŲ±ŲÆ ) ā¢ ā ļø
š- ŲŖŲ«ŲØŁŲŖ ( ŲØŲ§ŁŲ±ŲÆ ) ā¢ š°
š- Ų§ŁŲŗŲ§Ų” Ų§ŁŲŖŲ«ŲØŁŲŖ ā¢ āļø
š- Ų¶Ų¹ Ų§Ų³Ł + Ų§ŁŲ§Ų³Ł ā¢ š
š- Ų¶Ų¹ ŁŲµŁ + Ų§ŁŁŲµŁ ā¢ š
š- Ų¶Ų¹ ŲŖŲ±Ų­ŁŲØ + Ų§ŁŲŖŲ±Ų­ŁŲØ ā¢ ?
š- (ŲŖŁŲ¹ŁŁ Ų ŲŖŲ¹Ų·ŁŁ) Ų§ŁŲŖŲ±Ų­ŁŲØ ā¢ š
š- Ų§ŁŲ±Ų§ŲØŲ· ā¢ 
ć°ć°ć°ć°ć°ć°ć°ć°ć°ć°ć°
ŁŲ±ŁŲØ Ų§ŁŲØŁŲŖ@ZEPD8
",
'reply_to_message_id'=>$message->message_id, 
]);
}

if($text =="Ų§ŁŁŁŲŖ"){
bot('sendMessage',[
'chat_id'=>$chat_id,
'text'=>"š®š¶ Ų§ŁŲØŁŲÆ : š„Ų§ŁŲ¹Ų±Ų§Ł \n" . "āØš„  Ų§ŁŲ³ŁŁ  : " . date("Y") . "\n" . "š  Ų§ŁŲ“ŁŲ±š„ : " . date("n") . "\n" . "š«  Ų§ŁŁŁŁš„ :" . date("j") . "\n" . "š Ų§ŁŲ³Ų§Ų¹Łš„ :" . date('g', $time) . "\n" . "š Ų§ŁŲÆŁŁŁŁš„ :" . date('i', $time) . "\n" . " š",
'reply_to_message_id'=>$message->message_id
]);
}

if($text == "ŲŗŁŁ"){
bot( sendaudio ,[
 chat_id =>$chat_id, 
 audio =>"https://t.me/ANGAM_iq/4336",
 reply_to_message_id =>$message->message_id, 
]);
}

if($text == "ŁŁŁŲ§Ł"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"ŲÆŁŁŁ Ų®ŁŲ·ŲŖŁŁ ŁĢ·ŁŁŁŁŁŁ Ų®Ų§ŁŲŖŁ",
'reply_to_message_id'=>$message->message_id, 
]);
}
if($text == "ŁŁŁ ŁŲ§ŁŁŁ"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"ŁŲ§ŁŁŁ",
'reply_to_message_id'=>$message->message_id, 
]);
}
if($text == "1$"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"ŲŗŁŁŁŲ§ŁŁŁŪ ŁŁŲ“",
'reply_to_message_id'=>$message->message_id, 
]);
}
if($text == "Ų§Ų±ŁŲÆ ŲØŁŲŖ"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"Ų¶ŁŁŁŁ ŁŲµŲ¹ŁŁ Ų§ŲÆŁŁ Ų§ŁŁ Ų§ŲŖŁŲ§Ų¹Ł",
'reply_to_message_id'=>$message->message_id, 
]);
}


if($text== "Ų§ŁŲÆŁ ŁŁŲ±ŁŲØ"){
bot('sendMessage',[
"chat_id"=>$chat_id,
'text'=> 'ŁŲ§Ų° Ų§ŁŲÆŁ ŁŁŲ±ŁŲØ ' .$chat_id,
]);
}


if($text== "Ų§ŁŲÆŁŁ"){
bot('sendMessage',[
"chat_id"=>$chat_id,
'text'=>'Ų§ŁŲ§ŁŲÆŁ Ų§ŁŲ®Ų§Ųµ ŲØŁ : ' .$chat_id,
]);
}
if($text == "Ų“Ų³ŁŲ¬"or $text== "Ų“Ų³ŁŁ"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"ā½ ŁŁŁ°ŁŁŁŁŁŁ°ŁŲ“ āļø ŲŖŲ±ŁŲÆ ŲŖŲ²Ų­Ł š·",
'reply_to_message_id'=>$message->message_id, 
]);
}
if($text == "ŁŲ§"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"ŁŁŲ¬Ų¹Ų§ š",
'reply_to_message_id'=>$message->message_id, 
]);
}

if($text == "Ł4"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"Ų§ŁŁŲ§ ŲØŁ Ų¹Ų²ŁŲ²Ł ŁŁ ŁŲ§Ų¦ŁŲ© Ų§ŁŲ§ŲŗŲ§ŁŁš
āāāāāāāāāāā
šŲ§ŁŲ§ŲŗŲ§ŁŁ Ų§ŁŁŲŖŁŁŲ±Ł ŁĢ·ŁŁŁŁŁŁ 1Ų§ŁŁ10 Ų§ŲŗŁŁŁš¹ 
šŲ§ŁŲŖŲØ Ų§ŲŗŁŁŁ+Ų§ŁŲ±ŁŁ
ŁŲ«Ų§Łī®š»
Ų§ŲŗŁŁŁ1
Ų§Ł 
Ų§ŲŗŁŁŁ7
ŁŲ³ŁŁ Ų§Ų±Ų³Ł ŚµŁŚ± Ų§ŁŲ§ŲŗŁŁŁ

ć°ć°ć°ć°ć°ć°ć°ć°

",
'reply_to_message_id'=>$message->message_id, 
]);
}
if($text == "Ų§ŲŗŁŁŁ1"){
bot( sendaudio ,[
 chat_id =>$chat_id, 
 audio =>"https://t.me/mmss190/2663",
 reply_to_message_id =>$message->message_id, 
]);
}
if($text == "Ų§ŲŗŁŁŁ2"){
bot( sendaudio ,[
 chat_id =>$chat_id, 
 Group=>"https://t.me/ZEPD8",
 reply_to_message_id =>$message->message_id, 
]);
}
if($text == ""){
bot( sendaudio ,[
 chat_id =>$chat_id, 
 audio =>"https://t.me/mmss190/2657",
 reply_to_message_id =>$message->message_id, 
]);
}
if($text == "Ų§ŲŗŁŁŁ3"){
bot( sendaudio ,[
 chat_id =>$chat_id, 
 audio =>"https://t.me/mmss190/2656",
 reply_to_message_id =>$message->message_id, 
]);
}
if($text == "Ų§ŲŗŁŁŁ4"){
bot( sendaudio ,[
 chat_id =>$chat_id, 
 audio =>"https://t.me/mmss190/2652",
 reply_to_message_id =>$message->message_id, 
]);
}
if($text == "Ų§ŲŗŁŁŁ5"){
bot( sendaudio ,[
 chat_id =>$chat_id, 
 audio =>"https://t.me/mmss190/2643",
 reply_to_message_id =>$message->message_id, 
]);
}
if($text == "ŲÆŁ"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"ŁŲ§Ų®Ų·ŁŁ",
'reply_to_message_id'=>$message->message_id, 
]);
}
if($text == "Ų§ŲŗŁŁŁ6"){
bot( sendaudio ,[
 chat_id =>$chat_id, 
 audio =>"https://t.me/mmss190/2643",
 reply_to_message_id =>$message->message_id, 
]);
}
if($text == "Ų§ŲŗŁŁŁ7"){
bot( sendaudio ,[
 chat_id =>$chat_id, 
 audio =>"https://t.me/mmss190/2638",
 reply_to_message_id =>$message->message_id, 
]);
}
if($text == "Ų§ŲŗŁŁŁ8"){
bot( sendaudio ,[
 chat_id =>$chat_id, 
 audio =>"https://t.me/mmss190/2638",
 reply_to_message_id =>$message->message_id, 
]);
}
if($text == "Ų§ŲŗŁŁŁ9"){
bot( sendaudio ,[
 chat_id =>$chat_id, 
 audio =>"https://t.me/mmss190/2631",
 reply_to_message_id =>$message->message_id, 
]);
}

if($text == "Ų§ŲŗŁŁŁ10"){
bot( sendaudio ,[
 chat_id =>$chat_id, 
 audio =>"https://t.me/mmss190/2626",
 reply_to_message_id =>$message->message_id, 
]);
}
if($text == "Ų§ŲŗŁŁŁ11"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"ŁŲ§ŁŁ ŁŲ·Ų“ŲŖ",
'reply_to_message_id'=>$message->message_id, 
]);
}
if($text == "š"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"ŁŲ·ŁŲ± ŁŲ§ŲµŁŲ±ŁŁ Ų¬Ų§Ų±Ų©",
'reply_to_message_id'=>$message->message_id, 
]);
}

if($text == "š"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"ŁŲØŲ± ŁŁ ŲŗŲ±Ł",
'reply_to_message_id'=>$message->message_id, 
]);
}

if($text == "Ų§Ų³ŲŖŲ­Ł"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"Ų§ŁŁ Ų­ŁŁŲ§Ł ŁŲ³ŲŖŲ­Ł ŁĢ·ŁŁŁŁŁŁ ŁŁŲ³Ł ",
'reply_to_message_id'=>$message->message_id, 
]);
}

if($text == "š"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"Ų¹ŁŁŁŁ ŁŲ§ŲÆ Ų­ŁŁŁŁ Ų¬ŁŁ ŲØŲ³Ų·Ų§Ł",
'reply_to_message_id'=>$message->message_id, 
]);
}
if($text == "ŁŁŁ Ų§ŁŲ±ŲØŲ·"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"Ų“ŁŁ Ų§ŁŁŲÆŁŲ± ŁŲ§ŁŲ§ŲÆŁŁŁŁŁ",
'reply_to_message_id'=>$message->message_id, 
]);
}
if($text == "ŁŁŁ 1"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"ŁŲ§ Ų§ŁŁŁ ŁŁŁŪ ŲŖŁŲ·ŁŁŁ Ų“Ų³ŁŁ",
'reply_to_message_id'=>$message->message_id, 
]);
}

if($text == "š"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"Ų¹ŁŲÆ Ų«ŁŁŁ",
'reply_to_message_id'=>$message->message_id, 
]);
}

if($text == "š"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"ŁŲ²Ł Ų¹ŁŁŁā£Ģ“Ķ”Ķ”ŲÆĢ²ā£Ģ“Ķ”Ķ” ŁŁŁŁŁŚÆ ŁŁŁ",
'reply_to_message_id'=>$message->message_id, 
]);
}

if($text == "ŁŁŁ"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"Ų®Ų§ŁŲŖŁ Ų§Ł Ų³Ų­ŁŲ±Ł",
'reply_to_message_id'=>$message->message_id, 
]);
}
if($text == "ŲŖŲ­ŲØŁŁ"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"ŁŲ§Ų­ŲØ Ų²ŲØŲ§ŁŁ",
'reply_to_message_id'=>$message->message_id, 
]);
}
if($text == "ŲŖŁŲ±ŁŁŁ"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"Ų§ŁŲ«Ų± ŁŁ ŁŲ§ ŲŖŲŖŁŁŲ¹",
'reply_to_message_id'=>$message->message_id, 
]);
}

if($text == "ŁŲ¹Ų§Ł"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"ŲØŲ­ŁŁŁ ŁŲØŲ®Ų“ŁŁ",
'reply_to_message_id'=>$message->message_id, 
]);
}

if($text == "Ų±ŁŲ¹ ŁŲ¹Ų§Ł ŁŁŁŲ²"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"Ų§ŁŲ¹Ų¶Ł ŲŖŁ Ų±ŁŲ¹Ł ŁŲ¹Ų§Ł ŁŁŁŲ²šš",
'reply_to_message_id'=>$message->message_id, 
]);
}
if($text == "Ų±ŁŲ¹ Ų¹Ų¶Ł ŁŁŁŲ²"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"ŁŲ§Ų±ŁŲ¹Ł ŁŁŁŪ ŲŖŁŁŲŖ šš",
'reply_to_message_id'=>$message->message_id, 
]);
}

if($text == "ŁŁ" or $text =="ŁŁŁ" or $text == "ŁŁŁŁ" or $text =="ŁŁŁŁŁ" or $text=="ŁŁŁŁŁŁ"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"ā£{ŲÆŁŁŪŪŪŪ/ŁŁŲ§Ų±ŁŲØŁ_ŁŁŁŁ_ŁŁŁŁŁŁŁ/ŪŪŪŪŁŁ}ā£",
'reply_to_message_id'=>$message->message_id, 
]);
}

if($text == "ŁŁŁŁ"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"ŁŁŁŲ§ŲŖ Ų­ŲØŁ",
'reply_to_message_id'=>$message->message_id, 
]);
}

if($text == "Ų§Ų±ŁŲÆ ŁŁŲ²Ų±"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"Ų§ŲµŁŲ±ŁŁ ŁŁŲ²Ų±",
'reply_to_message_id'=>$message->message_id, 
]);
}

if($text == "Ų§ŁŲ³ŁŲ§Ł Ų¹ŁŁŁŁ"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>" ŁŲ¹ŁŁŁŁ Ų§ŁŲ³ŁŲ§Ł",
'reply_to_message_id'=>$message->message_id, 
]);
}
if($text == "Ų³ŁŁŁŁ" or $text ==" Ų¹ŁŁŁŲ±Ł "){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"Ų“ŁŲŖŁŲ±ŁŁŲÆ ŁŁŁŁŁ ŁŁŲ°Ł ŁŁŲ·ŁŁŲ±Ł",
'reply_to_message_id'=>$message->message_id, 
]);
}

if($text == "Ų§ŁŁŲ·ŁŲ±"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"@iOm3y",
'reply_to_message_id'=>$message->message_id, 
]);
}
if($text == "ŁŁŲ§"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"ŲŁŁŁŲ§ŲŖ Ų­ŁŲØŁ",
'reply_to_message_id'=>$message->message_id, 
]);
}
$MATHEO = explode('ŁŁŁ',$text);
if($MATHEO){
bot('sendMessage',[
'chat_id'=>$chat_id,
'text'=>$MATHEO[1],
]);
}

$mid = $message->message_id;
$memb = $update->message->message_id;
$id = $message->from->id;
$us = $update->message->from->username;
if($text == "Ų§ŁŲÆŁ" and  $you == "creator"){
$get_progile = file_get_contents("https://api.telegram.org/bot$API_KEY/getUserProfilePhotos?user_id=$id&limit=1");
$json = json_decode($get_progile);
$user_photo = $json->result->photos[0][0]->file_id;

bot('sendPhoto',[
'chat_id'=>$chat_id,
'photo'=>$user_photo,
'caption'=>"
šø ā¢ Ų§ŁŲÆŁŁ : $id
šø ā¢ ŁŲ¹Ų±ŁŁ : @$us
šø ā¢ ŁŁŁŲ¹Ł ā ŁŁŲ“Ų¦ Ų«ŁŁŁ šš„
šø ā¢ Ų±Ų³Ų§Ų¦Ł Ų§ŁŁŲ¬ŁŁŲ¹Ł ā $memb ",
'reply_to_message_id'=>$mid,
]);
}
if($text == "Ų§ŁŲÆŁ" and  $you == "administrator"){
$get_progile = file_get_contents("https://api.telegram.org/bot$API_KEY/getUserProfilePhotos?user_id=$id&limit=1");
$json = json_decode($get_progile);
$user_photo = $json->result->photos[0][0]->file_id;

bot('sendPhoto',[
'chat_id'=>$chat_id,
'photo'=>$user_photo,
'caption'=>"
šø ā¢ Ų§ŁŲÆŁŁ : $id
šø ā¢ ŁŲ¹Ų±ŁŁ : @$us
šø ā¢ ŁŁŁŲ¹Ł ā Ų§ŲÆŁŁ Ų·Ų§Ų“ šš
šø ā¢ Ų±Ų³Ų§Ų¦Ł Ų§ŁŁŲ¬ŁŁŲ¹Ł ā $memb ",
'reply_to_message_id'=>$mid,
]);
}
if($text == "Ų§ŁŲÆŁ" and  $you == "member"){
$get_progile = file_get_contents("https://api.telegram.org/bot$API_KEY/getUserProfilePhotos?user_id=$id&limit=1");
$json = json_decode($get_progile);
$user_photo = $json->result->photos[0][0]->file_id;

bot('sendPhoto',[
'chat_id'=>$chat_id,
'photo'=>$user_photo,
'caption'=>"
šø ā¢ Ų§ŁŲÆŁŁ : $id
šø ā¢ ŁŲ¹Ų±ŁŁ : @$us
šø ā¢ ŁŁŁŲ¹Ł ā Ų¹Ų¶Ł ŁŁŲŖŁŁ š¹ā
šø ā¢ Ų±Ų³Ų§Ų¦Ł Ų§ŁŁŲ¬ŁŁŲ¹Ł ā $memb ",
'reply_to_message_id'=>$mid,
]);
}


if($text == "ŲØŁŲŖŁ"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"ŁŲ§Ų§ ŁŁ ŁŲ§ŁŁŁ ŁŲ§Ų¹ŲÆ ŁŁŲ§ŁŁ ŁŁŁ ŲŖŲ±ŁŲÆ Ų“Ł ",
'reply_to_message_id'=>$message->message_id, 
]);
}

if($text == "Ų§ŁŲŖ"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"Ų“ŲØŁŁ ŁŲ§Ų¹Ų§Ų¬ŲØŁ ",
'reply_to_message_id'=>$message->message_id, 
]);
}

if($text == "ŁŲ§Ų§"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"ŁŁŲ¬Ų¹Ų§Ų§",
'reply_to_message_id'=>$message->message_id, 
]);
}

if($text == "Ų¬ŲØŁ"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"ŲÆŁ ŁŲŖŲ²Ų­Ł",
'reply_to_message_id'=>$message->message_id, 
]);
}

if($text == "Ų²Ų§Ų­Ł"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"ŁŁŁŁ Ų®Ł ŁŲ¬Ł ŁŲ²Ų­Ł Ų¹ŁŁŁ",
'reply_to_message_id'=>$message->message_id, 
]);
}

if($text == "Ų§Ų­ŲØŲ¬"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"Ų“ŲÆŲŖŲ­Ų³",
'reply_to_message_id'=>$message->message_id, 
]);
}

if($text == "ŲµŲÆŁ"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"ŁŲ§ŁŁŁ Ų“ŲØŁŁ",
'reply_to_message_id'=>$message->message_id, 
]);
}

if($text == "ŁŲ§ŁŁŁ"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"ŁŲŖŲ­ŁŁ",
'reply_to_message_id'=>$message->message_id, 
]);
}

if($text == "ŲØŁŲ³ ŁŁŲ±ŁŲØ"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"Ų§ŁŁŁŁŁŁŁŁŲ­Ų­Ų­Ł Ų®ŲÆŁŁ ŁŲ§ŁŲ­ ŁŲ­ŁŁ",
'reply_to_message_id'=>$message->message_id, 
]);
}

if($text == "Ų§ŲŖŁŁ"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"Ų­Ų­Ų­ŁŁ ŲŖŁŁŁŁŁ",
'reply_to_message_id'=>$message->message_id, 
]);
}

if($text == "Ų§ŲŖŁŁ Ų¹ŁŁ ŁŲ°Ų§"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"ŁŁŁŁ Ų³ŁŁŁŁ Ų±ŲÆ ŁŁŁŁ Ų§ŲŖŁŁ Ų¹ŁŁŁ",
'reply_to_message_id'=>$message->message_id, 
]);
}

if($text == "ŁŲ§ ŲŖŁŁ Ų¹ŁŁŁ"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"ŲŖŁŁŁŁŁ Ų¹ŁŁŁ ŁŲ¹Ł ŁŲµŲŖŁ ",
'reply_to_message_id'=>$message->message_id, 
]);
}

if($text == "ŲŖŁŁŁŲ“"or $text=="ŁŁŲ“"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"Ų®Ų§ŲØŲØŲØ ŲÆŁŁŁ",
'reply_to_message_id'=>$message->message_id, 
]);
}

if($text == "ŁŁŲ¹ŲØ"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"ŲÆŁŲ¬ŲØ Ų§ŁŲ¬ŲØ",
'reply_to_message_id'=>$message->message_id, 
]);
}

if($text == "ŁŲ·Ł"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"ŁŲ·Ł Ų§ŲØŁ Ų§ŁŁŲ·Ł",
'reply_to_message_id'=>$message->message_id, 
]);
}

if($text == "Ų§ŁŁŁ"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"ŁŁŁ ",
'reply_to_message_id'=>$message->message_id, 
]);
}

if($text == "ŁŲØ"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"Ų§Ų«ŁŁŁŁ\Ł",
'reply_to_message_id'=>$message->message_id, 
]);
}

if($text == "ŲµŲÆŲ§Ł"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"ŲŖŲ§Ų¬ Ų±Ų§Ų³Ł ŁŲ±Ų§Ų³Ł",
'reply_to_message_id'=>$message->message_id, 
]);
}
if($text == "Ų­ŲØŁ"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"ŲµŲ§Ų±ŲŖ ŁŲÆŁŁŁ ŁŲ³Ł Ų§ŁŲ¬ŲÆŁŲÆ ŁŁŁ Ų­ŲØŁ ",
'reply_to_message_id'=>$message->message_id, 
]);
}
if($text == "Ų“Ų³ŁŁ"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"SONIC",
'reply_to_message_id'=>$message->message_id, 
]);
}
if($text == "Ų³ŁŁŁŁ"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"ŁŲ§Ų§ Ų“ŲŖŲ±ŁŲÆ",
'reply_to_message_id'=>$message->message_id, 
]);
}

if($text == "Ų§Ų¶Ų­Ł"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"ŁŁŁŁŁŁ",
'reply_to_message_id'=>$message->message_id, 
]);
}
if($text == "Ų§ŲØŲ¬Ł"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"ŁŲ§ Ų§ŲØŲ¬Ł Ų­ŲØŁ",
'reply_to_message_id'=>$message->message_id, 
]);
}
if($text == "Ų§ŲØŲ¬Ł ŁŲÆŲ±Ł Ų§Ų¶Ų­Ł"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"Ų“ŁŁŁ Ų§Ų¶Ų­Ł ŁŲ“ŁŁŁ Ų§ŲØŲ¬Ł",
'reply_to_message_id'=>$message->message_id, 
]);
}

if($text == "ŁŲ§Ų§"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"ŁŲ§ŁŲ±ŲØ",
'reply_to_message_id'=>$message->message_id, 
]);
}
if($text == "5"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"Ų§Ų­Ų·Ł ŲØŁŁ ŁŲ§Ų·ŁŲ³Ł",
'reply_to_message_id'=>$message->message_id, 
]);
}
if($text == "1"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"Ų­Ų·Ł Ų§ŁŁ Ų¹ŲØŲÆ Ų§ŁŁŲ§Ų­ŲÆ",
'reply_to_message_id'=>$message->message_id, 
]);
}
if($text == "ŲŖŲÆŲ±Ų³"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"Ų“ŁŲÆŲ±Ų³ ŁŁŁ ŁŲ°Ų§ ŁŲ§ŁŁ",
'reply_to_message_id'=>$message->message_id, 
]);
}
if($text == "ŲµŲÆŁŁ"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"Ų¹ŲÆŁ Ų­Ų¬ŁŁ ŲŖŲ±Ł ŲØŁ Ų“Ų³ŁŁ",
'reply_to_message_id'=>$message->message_id, 
]);
}

if($text == "ŲŖŲ±ŁŲ­"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"Ų§Ł ŁŁŲ“ ŁŲ§",
'reply_to_message_id'=>$message->message_id, 
]);
}
if($text == "ŁŁ ŁŁŁ"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"ŁŁ Ų§ŁŲ¹Ų±Ų§Ł",
'reply_to_message_id'=>$message->message_id, 
]);
}
if($text == "Ų­ŁŲ§Ł"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"ŁŁŁŁŁ ŁŁŁ Ų­ŁŲ§Ł Ų§ŁŁŁ",
'reply_to_message_id'=>$message->message_id, 
]);
}
if($text == "Ų§Ų®ŁŁ"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"ŁŲ§ŁŁŲ¹Ł",
'reply_to_message_id'=>$message->message_id, 
]);
}
if($text == "ŁŲ±Ų®"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"ššŲ§ŁŲŖ Ų§ŁŁŲ±Ų®",
'reply_to_message_id'=>$message->message_id, 
]);
}
if($text == "Ų§ŁŲŖŁŁ"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"Ų“ŲØŁ Ų®ŁŲ“ ŲØŲ±ŁŲ§ŁŲ¬ Ų§ŁŁ Ų§Ų³ŲŖŲ¹ŁŁŁ",
'reply_to_message_id'=>$message->message_id, 
]);
}

if($text == "ŁŁŲ§ŲØŁ"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"ŁŁŲ“Ł ŲµŲ§Ų§Ų± ŲØŁŁŲ§ŲØŁ",
'reply_to_message_id'=>$message->message_id, 
]);
}
if($text == "ŲµŲ­"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"Ł ŁŲÆŲ§Ų¹ŲŖŁ ŲµŲ­Ų­",
'reply_to_message_id'=>$message->message_id, 
]);
}

if($text == "Ų®Ų·Ų§"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"ŁŁŲ“",
'reply_to_message_id'=>$message->message_id, 
]);
}


if($text == "ŲŖŲØŲ§ŲÆŁ"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"@iOm3y",
'reply_to_message_id'=>$message->message_id, 
]);
}



if($text == "Ų§ŁŲØŁŲ§ŲŖ"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"Ų“ŲØŁŁŁ",
'reply_to_message_id'=>$message->message_id, 
]);
}
if($text == "Ų²Ų§Ų­ŁŁ"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"Ų­Ł ŁŲ¶Ų­ŁŁŁ",
'reply_to_message_id'=>$message->message_id, 
]);
}
if($text == "ŁŁŁ Ų­ŲØŁŲØŁ"or $text=="ŁŁŁ Ų­ŲØŁŲØŲ¬"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"ŁŲ­ŲÆ ŁŲ§ŲØŁ ŁŲ«ŁŁ/Ų¬",
'reply_to_message_id'=>$message->message_id, 
]);
}
if($text == "Ų¬Ų§Ł"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"ŁŲ§Ų§Ų§ Ų“ŲØŁŁ Ų¶Ų¬ŲŖ",
'reply_to_message_id'=>$message->message_id, 
]);
}


if($text == "ŁŁŁ Ų¬Ų§ŁŁ"or $text== "Ų¬Ų§ŁŁ"or $text=="ŁŁŁ Ų¬Ų§Ų§ŁŁ"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"Ų“ŲØŁŁ Ų¶Ų¬ŲŖ ŁŁŁ ŁŁŁ Ų±Ų§ŁŲ­",
'reply_to_message_id'=>$message->message_id, 
]);
}

if($text == "Ų¹ŁŲÆ"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"ŁŲ§Ł Ų“Ų®Ų§Ų·",
'reply_to_message_id'=>$message->message_id, 
]);
}

if($text == "ŁŲ§Ų“Ł"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"ŁŲ«ŁŁ",
'reply_to_message_id'=>$message->message_id, 
]);
}
if($text == "ŲŖŁŁ ŲØŁŁ"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"ŁŲ§Ų§ Ų“ŲØŁŁ",
'reply_to_message_id'=>$message->message_id, 
]);
}


if($text == "Ų±Ų§ŁŲ­"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"Ų§ŁŁŁ ŁŁŲ§Ų§Ł",
'reply_to_message_id'=>$message->message_id, 
]);
}

if($text == "ŁŲŗŲ§ŲÆŲ±"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"ŲÆŁ Ų§ŁŁŁ ŁŁŲ§Ł",
'reply_to_message_id'=>$message->message_id, 
]);
}

if($text == "Ų“Ų¹ŁŁŁ"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"Ų§ŁŲ¬ŲØ",
'reply_to_message_id'=>$message->message_id, 
]);
}


if($text == "Ų§ŲØŲ±Ų§Ų±"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"ŁŲ§Ł Ų§Ł Ų¹ŁŁŁ Ų®ŲøŲ± ŁŲ±ŲÆŁ ŁŁ Ų§ŁŁŁ",
'reply_to_message_id'=>$message->message_id, 
]);
}

if($text == "Ų­ŁŁ"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"Ų§ŁŲŖ Ų§ŁŲ§Ų­ŁŲ§",
'reply_to_message_id'=>$message->message_id, 
]);
}if($text == "ŁŁŲØŁŲ§"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"Ų§Ų­ŲØ Ų®Ų§ŁŲŖŁ ",
'reply_to_message_id'=>$message->message_id, 
]);
}
if($text == "Ų±ŁŲ¹ Ų®Ų±ŁŁ"){
bot('sendMessage',[
'chat_id'=>$chat_id, 
'text'=>"ŲŖŁ Ų±ŁŲ¹ Ų®Ų±ŁŁ ŲØŁŲ¬Ų§Ų­ ā",
'reply_to_message_id'=>$message->message_id, 
]);
}
