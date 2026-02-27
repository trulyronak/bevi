# Bevi Quick Dispense

A simple toggle on/off button for Bevi touchless water dispensers. No more holding the button down.

## How It Works

1. Open the app on your phone
2. Scan the QR code on your Bevi machine
3. Tap **DISPENSE** to start water flow
4. Tap **STOP** when you're done

The app reverse-engineers the Bevi touchless WebSocket protocol (`wss://bevitouchless.co/user-side/{tabletId}/{token}`) and sends periodic dispense commands to keep the water flowing — the same way the original app does while you hold the button, except you just toggle it.

## Why

The official Bevi touchless experience requires you to tap and hold a button on your phone the entire time you're filling up. This is annoying. This app lets you tap once to start and once to stop.

## Deploy Your Own

It's a single `index.html` file. Deploy it anywhere that serves HTTPS (needed for camera access):

```bash
# Vercel
npx vercel deploy --prod

# Or any static host
# Just upload index.html
```

## URL Params

You can also skip the QR scanner by passing credentials directly:

```
https://your-deploy.vercel.app/?tabletId=XXXXX&token=YYYYY
```
