# datafusion_cdap_error_transformation_plugin
Complete example project to create a custom Google cloud datafusion (CDAP) error transformation plugin. Sourced and adapted from the documentation where there is no quickstart project.

## Error Transformation Plugin
An ErrorTransform plugin is a special type of Transform that consumes error records emitted from the previous stages instead of output records. It is used to transform an ErrorRecord to zero or more output records. In addition to the actual error object, an ErrorRecord exposes the stage the error was emitted from, an error code, and an error message. Errors can be emitted by BatchSource, Transform, and BatchAggregator plugins using the Emitter they receive. An ErrorTransform can be used in both batch and real-time data pipelines.

The only method that needs to be implemented is: transform()

## Methods
### initialize():
Used to perform any initialization step that might be required during the runtime of the ErrorTransform. It is guaranteed that this method will be invoked before the transform method.

### transform():
This method contains the logic that will be applied on each incoming ErrorRecord object. An emitter can be used to pass the results to the subsequent stage.

### destroy():
Used to perform any cleanup before the plugin shuts down.