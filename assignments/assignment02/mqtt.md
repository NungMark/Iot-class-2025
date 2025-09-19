# Exploring MQTT QoS Levels

Experiment with QoS 0, 1, and 2.
Observe how message delivery changes based on QoS settings.

## Publisher_qos.py output

```
/home/narin/Iot-class-2025-gateway/app/publisher_qos.py:20: DeprecationWarning: Callback API version 1 is deprecated, update to latest version
  client = mqtt.Client()
[16:46:43] DEBUG | Sending CONNECT (u0, p0, wr0, wq0, wf0, c1, k60) client_id=b''
Enter message to publish: [16:46:43] DEBUG | Received CONNACK (0, 0)
tungtungtuntungtungtungtungtungsahurahhhhhhhhhhhhhhhhhhhhhhh
Enter QoS level (0, 1, 2): 2
[16:46:59] DEBUG | Sending PUBLISH (d0, q2, r0, m1), 'b'test/qos/6510301047'', ... (60 bytes)
[16:46:59] PUBLISH REQUESTED | QoS=2 | Message='tungtungtuntungtungtungtungtungsahurahhhhhhhhhhhhhhhhhhhhhhh' | msgid=1
Enter message to publish: [16:46:59] DEBUG | Received PUBREC (Mid: 1)
[16:46:59] DEBUG | Sending PUBREL (Mid: 1)
[16:46:59] DEBUG | Received PUBCOMP (Mid: 1)
[16:46:59] PUBLISHED | msgid=1
[16:47:43] DEBUG | Sending PINGREQ
[16:47:43] DEBUG | Received PINGRESP
```

## Subscriber_qos.py Output

```
/home/narin/Iot-class-2025-gateway/app/subscriber_qos.py:25: DeprecationWarning: Callback API version 1 is deprecated, update to latest version
  client = mqtt.Client()
[16:46:18] DEBUG | Sending CONNECT (u0, p0, wr0, wq0, wf0, c1, k60) client_id=b''
[16:46:18] DEBUG | Received CONNACK (0, 0)
[16:46:18] Connected with result code 0
[16:46:18] DEBUG | Sending SUBSCRIBE (d0, m1) [(b'test/qos/6510301047', 2)]
[16:46:18] DEBUG | Received SUBACK
[16:46:59] DEBUG | Received PUBLISH (d0, q2, r0, m1), 'test/qos/6510301047', ...  (60 bytes)
[16:46:59] DEBUG | Sending PUBREC (Mid: 1)
[16:46:59] DEBUG | Received PUBREL (Mid: 1)
[16:46:59] RECEIVED | QoS=2 | Topic=test/qos/6510301047 | Message=tungtungtuntungtungtungtungtungsahurahhhhhhhhhhhhhhhhhhhhhhh | msgid=1
[16:46:59] DEBUG | Sending PUBCOMP (Mid: 1)
```