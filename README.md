### stormcrawler
---
https://github.com/DigitalPebble/storm-crawler

http://stormcrawler.net/

```java
// core/src/test/java/com/digitalpebble/stormcrawler/parse/filter/CSVMetadataFilter.java

public class CSVMetadataFilterTest extends ParsingTester {
  
  @Before
  public void setupParseBolt() {
    bolt = new JSoupParserBolt();
    setupParserBolt(bolt);
  }
  
  @Test
  public void testMultivalued() throws IOException {
    
    prepareParseBolt("test.parsefilters.json");
    
    Assert.assertEquals(1, output.getEmitted().size());
    List<Object> parsedTuple = output.getEmitted().get(0);
    Metadata metadata = (Metadata) parsedTuple.get(2);
    Assert.assertNotNull(metadata);
    String[] kws = metadata.getValues("keyword");
    Assert.assertNotNull(kws);
    Assert.assertEquals(12, kws.length);
  }
}

```

```
```

```
```


