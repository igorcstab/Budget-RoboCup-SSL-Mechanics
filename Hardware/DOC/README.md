 # Operation

A SSL bot during the competition, testing or maintenance has some operation particularities that should be met in the scope of hardware design in order to avoid headaches and make our lives easier. Those are being able to:

- Access the electronics and battery quickly;
- Repair a system without rendering the whole robot inoperative;
- Change the unified vision blobs easily;
- Have as little cable harness as possible (and organizing them, obviously);
- Keep a low center of gravity and be as lightweight as possible;
- Mitigate carpet contamination and clean the robot easily;

It doesn't look like much but those atributes will produce a lot of requisites or force design decisions. Pay attention to the fact each of those itens tells us **what** to do but not **how**.

# Requisites and Architecture

The Requisites are almost all rules related but there are a few that comes from somewhere else. For example, the omniwheels. Actually, using wheels could be a requisite and that document could easily have a hundred lines if we over-system-engineer it. But as I already wrote, it only exists to organize the workflow and ideas instead of pretending I work at Boeing.

The Architecture is structured as a Work Breakdown Structure (WBS) and is already something more or less subjective and if I review this part a few weeks from now I'll definitely disagree with the way I organized a few itens. Either way, this part of the Documentation has the purpose of guiding our mental efforts on decision making and our CAD organization instead of perfectly controlling how the project goes.

# Design Decisions

## Locomotion Motors

The motors I have available are those: [Locomotion Motors](https://microred.com.br/page18.html).

![loc_motor](https://user-images.githubusercontent.com/38017504/130149860-75d16333-8673-452b-bafb-11ce198a3771.jpg)

Also, because we're trying to cut costs the most we can, I'm going to use 3 motors per robot. Definitely 4 motors are better but 3 is the minimal number we should need to make our omnidirectional robot functional and it works decently (specially if you have access to more powerful motors and even better if you could have encoders). You could (actually, should) disagree with that decision but when you see that with 24 motors, you could manufacture 6 robots with 4 motors each while you'd need 18 motors for the same 6 bots team if they had 3 motors each, you can see there's a point at least. In fact, if you had 24 motors at your disposition, you could have 8 bots using 3 motors. That's 2 extra robots to substitute during the game. At least interesting, specially if they don't have batteries to play the full game. 

As we're talking about a soccer team, it means we should have more than a single robot. So competing in this category is much different than others that you'd need only one robot to perform a task. Here, each extra cost gets multiplied by the number of bots you intend to bring to the game. In the Division A, they play with 11 bots. Here, we're aiming at the Division B, as the intention would be entering the category, which is played with 6 bots and a smaller field. I could believe someone can make a 3-bots team work, but that would take a lot of programming effort and still would be a tough match against a 6 bots team because at each kickoff/fault/etc you'd have 1 robot to kick the ball. This way, is hard to keep coordination of the robots and keep them well positioned. So add the fact that's an AI that's taking those decisions and it's just not realistic imagine you'd have a chance. I believe that a 4-bots team should be able to play against any 6-bots team and it's a good number to give to your programming folks to test their ideas, implement strategies and adapt the behavior during a game. Any number beyond that is just a pay-to-win-ish way of improving the quality of your team instead of making they actually play better. Of course 6 is better than 4, but "code is free" while 2 extra robots increase your budget by 50%! During the 2019 Latin America Robotics Competition (LARC), I watched the best SSL game of my life between RoboCIn and Whartog Robotics B (which is our rookie's team. Basically we take some folks that don't know why you can plug your phone charger on the wall upside down and put them to design a whole SSL robot in the span of a year). It was a crazy close game that ended on 3x2 or 4x3 (I can't remember) for WR-B on overtime after both teams comebacks. RoboCIn has a pretty neat team with newly manufatured parts and they even compete internationally on Robocup Division B while WR-B had just a poor mechanics designed somewhere around 2014/15 with a straight kicker and a dream. I'd accept the claim "it was a fluke" because WR-B was playing worse although they won the game but that's only because they where at numeric and design disadvantage. Also the game went to overtime tied on 2x2 or something like that. Deserved.  Another case of that in my experience is the LARC 2016 Finals between RoboFei and WR, when WR 4 bots killing it. Anyway, just proving my point that 4 is a number that's good enough.

## Shaft Attachment

When it's not possible to remove the shaft from the motor, we'd have to design a hub to attach the wheel to the shaft instead of doing something stupid and ending with steel dust/chips inside the motor, degrading its lifetime. In my case, I'm going to design a hub anyway because I'm opting to leave the shaft as it is instead of making keyways, glueing a spur gear or whatnot. Also, **I'm not sure** about the material of the shaft but I'm assuming it's some stainless steel series. So, picking a material for the hub is not trivial given the many choices we have. Still, I don't believe you could make it resistant enough with regular PLA filament even with 100% infill and machining from a plastic like POM or PVC, altough exciting to experiment with in order to test if it would be eligible, it would still need a lot of inserts for the screws. Steel is granted to work. Same with many other metals like brass. So we'd like to have a material that isn't very expensive and that has good properties. Usually, copper alloys are more expensive and have specific applications which aren't being targeted here. Aluminium could work, but stainless steel in contact with aluminium reacts on a galvanic corrosion, weakening the hub. Wheter this is significant to our application, is questionable. Regular steel would be a good choice but the rust is a great downside in my opinion. So I choosed 304 stainless steel because is primarily easy to find, has a slightly higher price than aluminium, is machinable, not weldable (which is a desired feature, I guess?) and granted to work.

## Wheels

Scouting some old team's TDPs (Team Description Paper, which is a document teams from all around the world make telling what they do/did with their bots), we can already look for a trend on wheel diameter in order to make our first decision regarding that. Also, we know the basic concept: a small (diameter-wise) wheel produces more torque in cost of less displacement. What I found was a trend that the biggest wheels are about 60mm of diameter, while the smallest are about 45mm and sizes live somewhere in the middle gaussianly. Kind of. But most of the teams use pretty powerful motors when compared to what I have avaliable. So as one of their motors has more power than my whole robot, my decision is to stick at the low sized wheels to not bite off more than I can chew and to maximize the torque. My robots won't be able to run all over the field but they should work properly.

The number of sub-wheels/rubber wheels/whatever (which I'll call "O-rings" here) is not that critical. Numbers usually range from 15 to 20-ish. 

# Future Improvements

My project doesn't feature many functionalities both because it is minimalistic and meant to incentivise your own upgrades. Actually you don't **need** a dribbler or angled kicker. So if you want to cut everything down, you can even just go for the "straight kicker and a dream". Still, the following list contains some aspects to guide where you should start looking to reach a Division A, international tier design:

- A major improvement the robot could recieve is a dampened kicking system so when it intercepts the opponent or recieves a pass, the ball won't just bounce of the robot and go randomly somewhere;
- Upgrading to 4 motors, with higher power rating or of other type such as BLDC;
- Having encoders on the motors because there's basically no ~~decent~~ way to design a controller for the robot if you can't close the loop;
- Getting an IMU. It's a cool tool for the guys messing with the Control but it's more an electronics upgrade than something that should concern us. Even though, we should be aware of that and not design any wacky part for the robot: just try to keep everything balanced, symetric and don't stick anything in the middle of the bot;
