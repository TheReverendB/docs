** This page is outdated, and will be updated soon.**

# Setting up battles using `!bplan` and `!map`

Now that you know the basics of how to use `!map`, you can take advantage of another alias that helps make setting up an encounter much faster.  The `!bplan` alias allows you to set up an encounter and all of its combatants in advance.  By combining this time saver with the `!map` alias, we can get an encounter up and running during your session by running only two or three commands.  We’ll go through three different ways to work with both of these aliases.

Keep in mind that throughout this guide we will use brackets to signify `<required items>` and `[optional items]`.

## Beginner Level


#### 1.) First with !bplan

- Run the command: `!bplan new "<bplan name>" "<monster name>" [args]`.  Note the quotation marks.  These are not required, but will help prevent potential mismatches down the line.

`!bplan new “Ambush” “goblin” -n 4`

- If you want to add more monsters: `!bplan add “<bplan name>” “<monster name>” [args]`

`!bplan add “Ambush” “worg” -n 4`

- If you need to remove monsters you previously added: `!bplan remove “<bplan name>” “<monster name>” [args]`

`!bplan remove “Ambush” “worg” -n 4`

- When you're done adding monsters you can start your bplan with: `!bplan begin <bplan name>`

`!bplan begin ambush`


#### 2.) Next with !map

- Run  `!bplan begin <bplan name>` to get an initiative going

- Setup you map bg, options, size, etc. for your encounter. See [Getting Started](http://docs.otfbm.com/#/guides_getting_started) for basics.

> We have some preset maps you can use by using the command `!map -loadmap <map name>`
>
> To see a list of them type `!map maplist` (Currently there are two pages worth and you can view the second page by typing `!map maplist -page 2`)

- After you have gotten your map background, options, size, etc. setup now setup your monsters locations, size, token image, overlays, etc.

![](https://cdn.discordapp.com/attachments/695782699834540082/764230688387629066/Screen_Shot_2020-10-08_at_7.30.03_AM.png)

- After you have set up your encounter, run the command `!map -savebattle <bplan name>` to save the background, map size, token locations, and any other settings you’ve added to the encounter.

`!map -savebattle ambush`

![](https://cdn.discordapp.com/attachments/695782699834540082/764231326676549632/Screen_Shot_2020-10-08_at_7.31.42_AM.png)

- Now when your ready to run your encounter for your players you can type three commands

`!bplan begin ambush`

`!init add 20 DM -p`

`!map -loadbplan ambush`

- Then have your players join combat and have fun

## Moderate Level

You can add additional arguments in `!bplan` to spend less time setting things up in `!map`

- When adding monsters you can add notes which will allow you to place them in your map, set their size, and color right when you run `!bplan begin`

`!bplan add “ambush” "goblin" -note Location: b2 | Size: M | Color: r | Token: wtstw`

![](https://cdn.discordapp.com/attachments/695782699834540082/764233446703759365/Screen_Shot_2020-10-09_at_3.10.32_PM.png)

> Note that you can find the full list of valid size and color abbreviations by running `!map help`

- You then would set up a map background, size, options, etc. in `!map` and then run the command: `!map -savemap <map name>`

`!map -savemap ambush`

![](https://cdn.discordapp.com/attachments/695782699834540082/764236623692955708/Screen_Shot_2020-10-09_at_3.23.16_PM.png)

- When your ready to run your encounter you can run

`!bplan begin ambush`

`!init add 20 DM -p`

`!map -loadmap woods`

- Then have your players join combat and have fun

## Expert Level

You can set up a whole bplan with monsters, map background, size, options, etc. and just use `!bplan begin <battle name>` but this requires you to have knowledge on formatting with json and a text editor

- You can use this template for setting up your bplan in your text editor

```json
{
    "<bplan Name>": [
    "!init add 20 DM -p",
    "!i madd <Monster> -note \"Token: <token short code> | Location: <Grid Location>\" <Other Modifiers>",
    "!i effect DM map -attack \"||Size: <size> ~ Background: <url link> ~ Options: <options> ~ Objects: <object> ~ Walls: <wall>\""
    ]
}
```

Example

```json
{
      "Ambush":[
              "!init add 20 DM -p",
  "!i madd goblin -note \"Location: b2 | Size: M | Color: r | Token: wtstw\"",
  "!i effect DM map -attack \"||Size: 26x14 ~ Background: https://i.imgur.com/O2tMCFC.jpg ~ Options: dc60\""
    ]
}
```

- Copy code and then type in discord `!uvar bplans <paste code>`

![](https://cdn.discordapp.com/attachments/695782699834540082/764238746983333928/Screen_Shot_2020-10-09_at_3.31.43_PM.png)

- Then run `!bplan begin ambush` and it will set up everything
