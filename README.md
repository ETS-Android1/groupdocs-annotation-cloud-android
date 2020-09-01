# GroupDocs.Annotation Cloud SDK for Android
This repository contains GroupDocs.Annotation Cloud SDK for Android source code. This SDK allows you to work with GroupDocs.Annotation Cloud REST APIs in your Android applications on Java language.


## Installation
Add Internet permission in the AndroidManifest.xml. Example:
```xml
<manifest xmlns:android="http://schemas.android.com/apk/res/android" package="<package name>">
    <uses-permission android:name="android.permission.INTERNET" />
    ...
```

Add following repository and dependency to your android module's build.gradle
after "apply plugin: 'com.android.application'" section:
```
repositories {
    maven {
        url "https://repository.groupdocs.cloud/repo/"
    }
}

...
dependencies {
    ...
    implementation 'com.groupdocs:groupdocs-annotation-cloud:19.5'
}
```

## Getting Started

Please follow the [installation](#installation) instruction and use the following Java code:

```java
import com.groupdocs.cloud.annotation.client.*;
import com.groupdocs.cloud.annotation.model.*;
import com.groupdocs.cloud.annotation.api.InfoApi;


public class ApiExample {
                
    public static void getSupportedFormats() {

        //TODO: Get your AppSID and AppKey at https://dashboard.groupdocs.cloud (free registration is required).
        String appSid = "XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX";
        String appKey = "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX";

        Configuration configuration = new Configuration(appSid, appKey);

        InfoApi infoApi = new InfoApi(configuration);

        try {
            FormatsResult response = infoApi.getSupportedFileFormats();
            for (Format format : response.getFormats()) {
                System.out.println(format.getFileFormat());
            }
            
        } catch (ApiException e) {
            System.err.println("Failed to get supported file formats");
            e.printStackTrace();
            
        }

    }
}
```

## Licensing
All GroupDocs.Annotation Cloud SDKs are licensed under [MIT License](LICENSE).

[Home](https://www.groupdocs.cloud/) | [Docs](https://docs.groupdocs.cloud/annotation/) | [Demos](https://products.groupdocs.app/annotation/family) | [API Reference](https://apireference.groupdocs.cloud/annotation/) | [Source Code](https://github.com/groupdocs-annotation-cloud/groupdocs-annotation-cloud-android) | [Blog](https://blog.groupdocs.cloud/category/annotation/) | [Free Support](https://forum.groupdocs.cloud/c/annotation) | [Free Trial](https://purchase.groupdocs.cloud/trial)
