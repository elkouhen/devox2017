# Byte Buddy : la génération de bytecode facile ! (Nicolas Comet)

Exemple d'utilisation : simplifier la mise en place d'intercepteurs

```
Class<?> dynamicType = new ByteBuddy()
  .subclass(Object.class)
  .method(ElementMatchers.named("toString"))
  .intercept(FixedValue.value("Hello World!"))
  .make()
  .load(getClass().getClassLoader())
  .getLoaded();

assertThat(dynamicType.newInstance().toString(), is("Hello World!"));
```

