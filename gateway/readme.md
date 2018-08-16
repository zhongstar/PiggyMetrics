# Gateway service

## 1. Build gateway service docker image

### 1.1 Modify maven.xml to adapt to your environment

default maven-settings.xml adapt rainbond
```xml
<?xml version="1.0" encoding="UTF-8"?>

<settings xmlns="http://maven.apache.org/SETTINGS/1.0.0"
          xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
          xsi:schemaLocation="http://maven.apache.org/SETTINGS/1.0.0 http://maven.apache.org/xsd/settings-1.0.0.xsd">

  <mirrors>
    <mirror>
      <id>rainbond-mirror</id>
      <mirrorOf>*</mirrorOf>
      <name>rainbond-mirror</name>
      <url>http://maven.goodrain.me/</url>
    </mirror>
</mirrors>

</settings>

```

### 1.2 Build gateway image

```bash
docker build -t gateway .
```

## 3. ENV

| Name |Default Value |Info|Required|
|---------|-------------|-------|--------|
| PORT |4000| Server Port| NO |
| CONFIG_SERVICE_PASSWORD| NULL | Service Password|Yes|

## 3. Local test

```bash
docker run -it -e CONFIG_SERVICE_PASSWORD=pass4you config
```

