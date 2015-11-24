# libphonenumber-plist
A mapping between country region codes supported by libphonenumber and their associated dialing codes

Generated using the following code:

```scala
import com.google.i18n.phonenumbers.PhoneNumberUtil
import scala.collection.JavaConversions._

val util = PhoneNumberUtil.getInstance
val map = util.getSupportedRegions.toSet.map { x: String => x -> util.getCountryCodeForRegion(x) }
map.foreach { case (k, v) => println(s"<key>$k</key>"); println(s"<string>$v</string>") }
```
