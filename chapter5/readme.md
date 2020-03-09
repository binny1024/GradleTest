```java
/**
 * Applies zero or more plugins or scripts.
 * <p>
 * The given closure is used to configure an {@link ObjectConfigurationAction}, which “builds” the plugin application.
 * <p>
 * This method differs from {@link #apply(java.util.Map)} in that it allows methods of the configuration action to be invoked more than once.
 *
 * @param closure the closure to configure an {@link ObjectConfigurationAction} with before “executing” it
 * @see #apply(java.util.Map)
 */
void apply(Closure closure);

/**
 * Applies zero or more plugins or scripts.
 * <p>
 * The given closure is used to configure an {@link ObjectConfigurationAction}, which “builds” the plugin application.
 * <p>
 * This method differs from {@link #apply(java.util.Map)} in that it allows methods of the configuration action to be invoked more than once.
 *
 * @param action the action to configure an {@link ObjectConfigurationAction} with before “executing” it
 * @see #apply(java.util.Map)
 */
void apply(Action<? super ObjectConfigurationAction> action);

/**
 * Applies a plugin or script, using the given options provided as a map. Does nothing if the plugin has already been applied.
 * <p>
 * The given map is applied as a series of method calls to a newly created {@link ObjectConfigurationAction}.
 * That is, each key in the map is expected to be the name of a method {@link ObjectConfigurationAction} and the value to be compatible arguments to that method.
 *
 * <p>The following options are available:</p>
 *
 * <ul><li>{@code from}: A script to apply. Accepts any path supported by {@link org.gradle.api.Project#uri(Object)}.</li>
 *
 * <li>{@code plugin}: The id or implementation class of the plugin to apply.</li>
 *
 * <li>{@code to}: The target delegate object or objects. The default is this plugin aware object. Use this to configure objects other than this object.</li></ul>
 *
 * @param options the options to use to configure and {@link ObjectConfigurationAction} before “executing” it
 */
void apply(Map<String, ?> options);
```