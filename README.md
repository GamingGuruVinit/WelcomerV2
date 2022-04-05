⌄
⌄
const Discord = require('discord.js')
const client = new Discord.Client()

client.on("ready", async () => {
  console.log(`Bot is has been deployed 🚀`)
  client.user
    .setActivity(`GamingGuruVinit`, { type: "WATCHING" }) //status code
    .catch(error => console.log(error))
})

const canvacord = require("canvacord")

client.on("guildMemberAdd", async member => {
  if(member.guild.id !== "959480855909240873") return;
  const welcomeCard = new canvacord.Welcomer()
  .setUsername(member.user.username)
  .setDiscriminator(member.user.discriminator)
  .setAvatar(member.user.displayAvatarURL({ format: "png" }))
  .setColor("title", "#1F1DFF") //white
  .setColor("username-box", "#FF610A") //white
  .setColor("discriminator-box", "##1AFFE9") //white
  .setColor("message-box", "##FF0000") //white
  .setColor("border", "#000000") //black
  .setColor("avatar", "#FEFCFC") //white
  .setBackground("https://media.discordapp.net/attachments/947019548597571654/959110642768424980/images_-_2022-03-31T205203.339.jpeg") //should be png format
  .setMemberCount(member.guild.memberCount)
  let attachment = new Discord.MessageAttachment(await welcomeCard.build(), "welcome.png")
  member.guild.channels.cache.get("959492082207182938").send(member.user.toString(), attachment)
})


client.login(process.env.token)
Files
365Gaming
365Gaming
const mySecret = process.env['token']
