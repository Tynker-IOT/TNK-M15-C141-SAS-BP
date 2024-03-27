Sync LED to Node-red
======================




In this activity, you will send the LED status data to the Node-red using MQTT server.


![]=(https://s3.amazonaws.com/media-p.slid.es/uploads/1525749/images/11181691/image__49_.png)


Follow the given steps to complete this activity:
1. Open the file `sketch.ino`.




2. Define a String lightStatus as `Off`.
```
String lightStatus = "Off";
```


3. Change the light status as per illumination value.
```
  if(lux < 500)
  {
    digitalWrite(LED_PIN, HIGH);
    // Set lightStatus to on
    lightStatus ="On";
  }
  else{
    digitalWrite(LED_PIN, LOW);
    // Set lightStatus to on
    lightStatus ="Off";
  }
```


4. Publish the light status to /LightStatus.
```
client.publish("/LightStatus", lightStatus.c_str());
```


5. Save and run the simulation to check the output.
