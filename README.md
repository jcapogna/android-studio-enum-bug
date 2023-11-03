This is an example repository demonstrating that Android Studio cannot recognize enums in the `io.appflags:appflags-java-protobuf-types` library.  

This library works in IntelliJ and all enums can be used. 

Corresponding errors in idea.log:

```
2023-11-03 14:58:57,205 [   4397]   WARN - #o.j.j.d.IdeaDecompiler - Inconsistent generic signature in method <init> (Ljava/lang/String;II)V in io/appflags/protos/ConfigurationLoadType [io/appflags/protos/ConfigurationLoadType]
2023-11-03 14:58:57,313 [   4505]   INFO - #c.i.p.i.c.ClassFileStubBuilder - /Users/justin/.gradle/caches/modules-2/files-2.1/io.appflags/appflags-java-protobuf-types/1.0.2/c5afbe59580f0678d1133deafc1d3d786e039b4b/appflags-java-protobuf-types-1.0.2.jar!/io/appflags/protos/ConfigurationLoadType.class: /Users/justin/.gradle/caches/modules-2/files-2.1/io.appflags/appflags-java-protobuf-types/1.0.2/c5afbe59580f0678d1133deafc1d3d786e039b4b/appflags-java-protobuf-types-1.0.2.jar!/io/appflags/protos/ConfigurationLoadType.class: Cannot invoke "String.length()" because "text" is null
```

This error impacts all enums in this library. The enums in this library are generated from protobufs. 

One enum not loading is ConfigurationLoadType. The protobuf definition is:

```protobuf
enum ConfigurationLoadType {
  INITIAL_LOAD = 0;
  PERIODIC_RELOAD = 1;
  REALTIME_RELOAD = 2;
}
```