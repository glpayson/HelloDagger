### tl;dr setup of https://github.com/google/dagger

#### Using: 
- Dagger 2
- Maven
- IntelliJ IDEA

#### Steps:
- Add Dagger 2 dependency
```xml
<dependency>
    <groupId>com.google.dagger</groupId>
    <artifactId>dagger</artifactId>
    <version>2.x</version>
</dependency>
```
- Add maven-compiler-plugin and dagger-compiler
```xml
<build>
  <plugins>
    <plugin>
      <groupId>org.apache.maven.plugins</groupId>
      <artifactId>maven-compiler-plugin</artifactId>
      <version>3.6.1</version>
      <configuration>
        <annotationProcessorPaths>
          <path>
            <groupId>com.google.dagger</groupId>
            <artifactId>dagger-compiler</artifactId>
            <version>2.x</version>
          </path>
        </annotationProcessorPaths>
      </configuration>
    </plugin>
  </plugins>
</build>
```
- Turn on ```Enable annotation processing``` in IntelliJ
    
    * ```Settings``` --> search ```Annotation Processors``` -->  ```Enable annotation processing```
    
- ```mvn clean complile```

    * IntelliJ will complain about not being able to find symbol for ```DaggerCoffeeApp_Coffee``` until it is generated during ```compile```
    * Generated classes are in ```target/generated-sources/annotations/coffee```
