# Toaster multiple devices example

This is an extended version of a [Toaster device example](../lighty-toaster-device).

The simulator has the ability to create multiple devices in a single JVM instance. **All devices share the same datastore.**

### Build and run
Build root project - for more details check: [README](../../../README.md)

**Run device**
* Extract binary distribution in target directory.
* Run jar file from zip with parameters. Parameters are optional. If they are not used, the default value is used.  
`--device-count DEVICES-COUNT` (Default 1) Number of simulated netconf devices to spin. This is the number of actual ports which will be used for the devices. If some ports are bound, these ports will be skipped. The log shows all open ports.    
`--starting-port STARTING-PORT` (Default 17380) First port for simulated device. Each other device will use incremented port number.    
`--thread-pool-size THREAD-POOL-SIZE` (Default 8) The number of threads to keep in the pool, when creating a device simulator, even if they are idle.    
```
java -jar lighty-toaster-multiple-devices-13.2.1-SNAPSHOT.jar --starting-port 20000 --device-count 200 --thread-pool-size 200
```
* All devices are accessible via a bound port. For more information on the functionality of this simulator check: [README](../lighty-toaster-device/README.md).