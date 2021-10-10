# Gabut Doank

Monggo di pake... :v

## CARA INSTALL DI TERMUX

```bash
//Const
const fetch = require('node-fetch')

//Function
const sendMediaURL = async(to, url, text="", mids=[]) =>{

                if(mids.length > 0){

                    text = normalizeMention(to, text, mids)
                }
                const fn = Date.now() / 10000;
                const filename = fn.toString()
                let mime = ""
                var download = function (uri, filename, callback) {
                    request.head(uri, function (err, res, body) {
                        mime = res.headers['content-type']
                        request(uri).pipe(fs.createWriteStream(filename)).on('close', callback);
                    });
                };
                download(url, filename, async function () {
                    console.log('done');
                    let media = fs.readFileSync(filename)
                    let type = mime.split("/")[0]+"Message"
                    if(mime === "image/gif"){
                        type = MessageType.video
                        mime = Mimetype.gif
                    }
                    if(mime.split("/")[0] === "audio"){
                        mime = Mimetype.mp4Audio
                    }
                    hexa.sendMessage(to, media, type, { quoted: mek, mimetype: mime, caption: text,contextInfo: {"mentionedJid": mids}})
                    
                    fs.unlinkSync(filename)
                });
            }

//Case
anu = await fetchText('https://raw.githubusercontent.com/myname31/Random/main/asupan.txt')            
.then(async (body) => {              
anu = body.split('\n')             
anu = anu[Math.floor(Math.random() * anu.length)]             
sendMediaURL(from, anu)

})```
