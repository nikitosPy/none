```py
@bot.command()
async def user(ctx):
    await ctx.channel.purge(limit = 1)
    img = Image.new('RGBA', (400, 200), '#232529')
    url = str(ctx.author.avatar_url)[:-10]
    response = requests.get(url, stream = True)
    response = Image.open(io.BytesIO(response.content))
    response = response.convert('RGBA')
    response = response.resize((100, 100), Image.ANTIALIAS)
    img.paste(response, (15, 15, 115, 115))
    idraw = ImageDraw.Draw(img)
    name = ctx.author.name # Fsoky
    tag = ctx.author.discriminator 
    headline = ImageFont.truetype('arial.ttf', size = 20)
    undertext = ImageFont.truetype('arial.ttf', size = 12)
    idraw.text((145, 15), f'{name}#{tag}', font = headline) # Fsoky#9610
    idraw.text((145, 50), f'ID: {ctx.author.id}', font = undertext)
    img.save('user_card.png')
    await ctx.send(file = discord.File(fp = 'user_card.png'))
```
