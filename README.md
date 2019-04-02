# Barcode4J

Barcode4J is a flexible generator for barcodes written in Java. 

This repository contains the code of the Barcode4J library originally
published at http://barcode4j.sourceforge.net. It reflects the CVS `trunk`
as of 2019-04-02 - that is, the version that was never released as a v2.2.
Please see http://barcode4j.sourceforge.net/trunk/index.html for the
appropriate documentation.

Configuration and a release tag have been added so that https://jitpack.io can be used to
include Barcode4J as a dependency in other projects. See https://jitpack.io/#mpdude/barcode4j/2.2.0-SNAPSHOT-20190402.1
for detailed instructions.

In particular, if you want to use this library to include QR codes in
documents created using Apache FOP, add the following Maven dependencies:

```xml
  <repositories>
      <repository>
          <id>jitpack.io</id>
          <url>https://jitpack.io</url>
      </repository>
  </repositories>

  <dependencies>
    <dependency>
        <groupId>com.github.mpdude.barcode4j</groupId>
        <artifactId>barcode4j-fop-ext</artifactId>
        <version>2.2.0-SNAPSHOT-20190402.1</version>
    </dependency>

    <dependency>
    	<groupId>com.github.mpdude.barcode4j</groupId>
        <artifactId>barcode4j</artifactId>
        <version>2.2.0-SNAPSHOT-20190402.1</version>
    </dependency>

    <!-- Include ZXing Core 1.7 as per http://barcode4j.sourceforge.net/trunk/symbol-qr.html -->
    <dependency>
        <groupId>com.google.zxing</groupId>
        <artifactId>core</artifactId>
        <version>1.7</version>
    </dependency>
  </dependencies>
```

You can then use the folling in FOP:

```xml
<fo:block>
  <fo:instream-foreign-object>
    <barcode:barcode xmlns:barcode="http://barcode4j.krysalis.org/ns" message="https://github.com/mpdude/barcode4j">
      <barcode:qr>
        <barcode:module-width>.5mm</barcode:module-width>
        <barcode:encoding>ISO-8859-1</barcode:encoding>
        <barcode:ec-level>L</barcode:ec-level>
      </barcode:qr>
    </barcode:barcode>
  </fo:instream-foreign-object>
</fo:block>
```

# License

Barcode4J is licensed under the the Apache License, Version 2.0.
The license text can be found under legal/barcode4j.LICENSE.txt.
