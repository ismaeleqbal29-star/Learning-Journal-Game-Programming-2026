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

## 22/11/2026
Today I did some research on how to make my breakable blocks component, I want the blocks to break when the player either hits them by jumping, attacking or landing on them but only during the "night" according to the timer i made previously, Paul mentioned that there is a way I could do this without making them rely on each other using a toggle, so I decided to figure out the actual breaking part first, I watched a bunch of tutorials and checked out a bunch of documentations and forum discussions but then I found this tutorial which make Mario style breakable blocks that break from the bottom so I used his method of breaking the blocks without the extra parts of only breaking from below and only the player breaking them because for now I just wanted that when a collider hits them they break, [Mario Style Breakable Blocks](https://www.youtube.com/watch?v=0WReDQ8ZSIA).

I managed to get the breakable blocks working, I added some "blocks" into the scene with some balls that fall from above them and the blocks break on impact which is good, it means the breaking works, it took me some time to get the breaking working, the script works by using Unity Events and I was first triggering the wrong function which was annoying for a while and then I figured it out.

I then tried to figure out how to make the toggling toggle-able, however I couldn't figure out how to do that, I tried using an `if` statement, but I don't think I fully understand how to use 'if' statements enough to get it to work. I then tried using AI to help me figure it out and it was giving some helpful solutions but I don't think it was what I was looking for, so I asked it to show what resources it had gotten it's answers from to see if I could try to understand it and be able to use that knowledge to figure it out, unfortunately that didn't really work out, I suspect it will be something with either an `if` statement or a `bool`, unfortunately I do not at this moment in time know, so that is an issue I need to work on for this component
- [x] blocks breaking on impact working
- [ ] need to figure out how to make them break only when specific conditions are met.

## 24/11/2026
Today I sat down with Paul and he helped me make the blocks break only when the game thinks it is night, we did that by using Unity Events, similar to how I made the blocks break in the first place, we went back to the timer component and made it so that when each time of day is triggered, it activates a Unity Event, which I need to add in the documentation for that. Inside of the `BreakableBlocks` script I added a `bool` which dictates whether or not it is day and if day equals false, meaning night, the blocks will break.

Now this script technically will work but it needs a timer to tell it whether or not it is day, for that, we created a test script that will drop two balls, one during the day so it won't break the blocks and one that drops at night so that the ball will break and in that test script, we had a `Coroutine` that waited for a set amount of time and then set the game to day and releases a ball, and then once the first ball has been released, it waits another set amount of time before setting the game to night and releases the second ball which breaks the block.

To change between the two states of time, we added two Unity Events, one for day and one for night in the test script and then hooked everything together inside the `Inspector`, to do this I created an empty object called `TestBlocks` and attached the script to that and in the `Event System` there was two events, `onNight` and `onDay` and then hooked the blocks up to the events and in `onNight` I didn't tick the box to making it day and in the `onDay` event, ticked the box making it night.

Whilst adding the Unity Events, it came up with an error and because this had happened to me before, I knew what was wrong, it was because I didn't put `using UnityEngine.Events` at the top which is something I check often when an error comes up, is the correct `using` at the top of the script, such as what happened today.

This means that my checklist from last time is completed but I need to add another thing:
- [x] blocks breaking on impact working
- [x] need to figure out how to make them break only when specific conditions are met.
- [ ] need to add Documentation explaining the script and need to update the documentation for the timer and make sure everything is organised accordingly.

## 25/11/2026
Today I didn't really do a lot from a coding point of view, I just began the documentation for the `Breakable Blocks` Component, and i also updated the documentation for the `DayNightTimer` Component which was good, I do now believe that it is completely done thankfully, I do wish i did more work today but didn't really get a lot done unfortunetely.

## 26/11/2026 (kinda)
It is currently half past midnight and I decided that before I go to bed, I will finish off the documentation because I didn't have a lot left to do, just a couple of lines left and then I just wanted to reorganise my folders inside of my Unity Projects because Paul said it would be better if all the needed folders were inside of one folder named the component as it would be easier to export, I think. So I did that all relatively quickly and now I should be done, with those two components, apart from the videos I have to record of them. The only annoying thing that I would like to figure out if possible is why GitHub seems to hate me, every-time I work on components and add changes, they don't register in GitHub Desktop and I don't know why, I have tried soo many different ways to get it to work and it doesn't seem to help, the best thing I can do for now is every time I work on it, I have to go and manually paste my assets folder from Unity into GitHub so it replaces the old one and only then does it register in GitHub, slightly annoying but the best I got right now. At least I can now update my checklist for this component.
- [x] blocks breaking on impact working
- [x] need to figure out how to make them break only when specific conditions are met.
- [x] need to add Documentation explaining the script and need to update the documentation for the timer and make sure everything is organised accordingly.
