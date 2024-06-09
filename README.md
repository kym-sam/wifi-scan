## Git clone - wifi-scan

```
git clone https://github.com/kym-sam/wifi-scan.git
```

# index.js
```ts
// npm init -y
// npm install node-wifi

const wifi = require('node-wifi');

wifi.init({
  iface: null 
});


wifi.scan()
  .then(networks => {
    if (networks.length === 0) {
      console.log('No Wi-Fi networks found.');
    } else {
      console.log('\nFound Wi-Fi Networks:\n');
      networks.forEach(network => {
        console.log(`SSID: ${network.ssid}`);
        console.log(`BSSID (MAC): ${network.bssid}`);
        console.log(`Signal Level: ${network.signal_level}`);
        console.log(`Frequency: ${network.frequency}`);
        console.log(`Channel: ${network.channel}`);
        console.log(`Security: ${network.security}`);
        console.log('\n');
      });
    }
  })
  .catch(error => {
    console.error('Error scanning Wi-Fi networks:', error);
  });

```
