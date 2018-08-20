# pushcore
Library to send push notification for APN and GCM (deprecated soon!)

```java
public static void main(String[] args) {
	// Android GCM
	String apiKey = "AIzaSyAit-7GrfhqiA-pBh8XTN1W4azyFGPrRBY";
	PushService.configGCM(apiKey);
	JsonObject additionalData = new JsonObject();
	additionalData.addProperty("foo", "bar");
	String[] gcmTokens = {"cmTJjM9TdDU:APA91bHQMRkY34laUzq0Q03tBCPg23WpRVwwVAR_o-0tMUjqKaOniGx9uxlGRNjK489GzMOfIYkGMUgML2tiqbtNLY6ltTNYtYthuAvilLS4Dcs0EySubrCvoJ3WqZq0njEcEPqm2ewOfe8TihNRWEmaKRV-jaWVHw"};
	System.out.println(PushService.pushGcm(gcmTokens, "Thông báo", "Thông báo thay đổi thời khóa biểu", additionalData));
	
	
	// iOS APN
	boolean isProduction = true;
	String p12Path = System.getProperty("user.home")+ File.separator + "ischooljob" + File.separator + "ischool_push.p12";
	String password = "...";
	PushService.configAPN(isProduction, p12Path, password);
	JsonObject additionalData2 = new JsonObject();
	additionalData2.addProperty("foo", "bar");
	int badge = 1;
	String[] apnTokens = {"3e1d79e426ea32fb148b871bf820ef2dc7287be4b7a63ab824a978bd50b0e6a5", "..."};
	System.out.println(PushService.pushApn(apnTokens, "titlte", "content", badge));
}
```
