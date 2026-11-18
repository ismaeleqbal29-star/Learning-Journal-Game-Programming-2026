# My Learning Journal
## 27/10/2026
First entry, today we looked at a dialogue system, first Paul was demonstrating how to code it and was asking us how we could code this as we went along, then he got us to with him however we ran out of time so we are supposed to figure it out on our own.

While working on it in class, i ran into a small issue of the component not reading the script but i solved it by deleting the component and then re-adding it.

## 9/11/2026
Today I tried to the `Dialogue System` we started with Paul last session, however, whilst following the video Paul sent, I had a strange error pop up complaining about the `IEnumerator`, the error specifically was saying that `The type or namespace name 'IEnumerator' could not be found (are you missing a using directive or an assembly reference?)` I don't know exactly what that means and it is getting quite late so I am going to ask Paul about it tomorrow and see if it can be fixed, everthing else was working, it was just when trying to implement a typing out feel to the text otherwise everything else was working.

## 10/11/2026
Today Paul helped me fix the error by just adding at the top of my script, `using System.Collections` which fixed the error, I thought I tried that yesterday but clearly not

## 15/11/2026
Today I began to work on my components for this module, the first one I decided to tackle was the persistent timer/day night cycle which i wanted to call a function every x amount of time which would then trigger other component. The route I decided to go for this component was to use the `InvokeRepeating` function which would allow me to repeat a function with a set amount of time in between, I scripted it and added a `Debug.Log` message so I could see whether or not it was working and thankfully it was.
However, I wanted to be able to change the variables of the time between triggering the function inside of unity so I tried to make a public float which i could then change, but some reason it wasn't liking that and was asking for context, for now i have turned those lines of code off by using `//` in front of the lines but i will try to figure that out.
Another thing i have realised is that I want to call two different functions and i want them to alternate between the two, so i suspect this component will be a bit more complicated however, this is my progress so far.

### Problems Today
Just to list down todays "problems", I am not able to change the time variables for the `InvokeRepeating` inside of unity, and I want to be able to call two functions and alternate between the two.

## 17/11/2026
Paul helped me solve the issue of not being able to change the variables within Unity, turns out I tried every way to do it but the correct way which was `public float timerStart;` when i did it, I added an extra name which wasn't needed, so now I am able to change the variables within Unity which is good.

Then I asked Paul about whether or not I would need to alternate between functions for the day/night cycle and he suggested using a toggle so that instead of using two different functions, it works by toggling the function true then false and alternates, hopefully that will work as I need it to but I won't find out till later I suppose.

I was also having issues with GitHub where it wasn't registering the changes I had made in the previous days, but I just copied over the assets folder from Unity to GitHub as Paul suggested and I think it has fixed itself, don't really know, not very good at using GitHub.

## 18/11/2026
Today I added some `Documentation` to my Unity file which explains what my script does, didn't have too much trouble writing that, I did have an issue with GitHub not recognising my changes again so I tried the fix I did yesterday which did work but it also accidentally got rid of my `Assets` folder in Unity so I copied it from GitHub in Finder, I really need to properly figure out how to use GitHub but other than that, I didn't have any issues today. The documentation has been fully added, I used the documentation I wrote last year for reference but thankfully this script isn't very complicated, I think I am done with this component all being well, I can't think of anything that needs adding or changing with it so I think I am ready to move onto the next component which will either be the sprite swapper or the breakable blocks, I'm not very sure yet, I might do the breakable blocks as it will probably be simpler than the sprite swapper. One other thing I need to figure out for this module is how to calculate my total hours I'm working a day for my `Work Log`, that and remembering to do it
