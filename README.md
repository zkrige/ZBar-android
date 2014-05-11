ZBar-android
============

Android dropin to scan barcodes using ZBar


Usage:
======
1) compile zbar-android
2) add zbar-android to your libs folder
3) declare the activity in your android manifest as follows
```
<application
	.
	.
	.
    <activity android:name="com.zayinkrige.barcode.BarcodeScan"></activity>
</application>
```
4) start the barcode scanner 
```
Intent intent = new Intent(this, BarcodeScan.class);
startActivityForResult(intent,999);
```
5) get barcode result
```
protected void onActivityResult(int requestCode, int resultCode, Intent intent) {
	switch (requestCode) {
	case 999:
		if (resultCode == RESULT_OK) {
			String barcode = intent.getExtras().getString("barcode");
		}
		break;
	default:
		break;
	}
}
```