# Timber
Customized version derived from JakeWharton's timber project. Flexible logging tool for android, writing message and errors into files.

# Basic Usage:
Create a Tree factory with annotations to control logging behaviors.
```
public interface TreeFactory {
    @Paper("{\"Thread\":\"http-thread\",\"Class\":\"SampleActivity\"," +
            "\"Filters\":[\"V\",\"I\",\"W\",\"E\",\"A\"]}")
    @Echo("{\"Level\":\"W\"}")
    Tree createTree();

    @Custom("{\"Package\":\"woods.log.sample\"}")
    CatcherTree createCatcherTree();
}
```
And then build init Timber with builder()
```
Timber.builder()
        .addTreeFactory(TreeFactory.class)
        .build();
```
