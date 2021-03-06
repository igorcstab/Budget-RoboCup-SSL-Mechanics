# Licensing
Long story short, the Open Source Hardware Association (OSHWA) basycally says although you can use the software licenses for hardware, it's not ideal. Also, if you really open the GNU GPL license text, for example, and read it once in your life, you'll have to agree it's only suited for software even though people use it for other types of products. So the OSHWA suggests the use of a software license for licensing software, a dedicated license for documentation and a proper hardware license on your project.

For that reason, the **Documentation** of this project is licensed under **CC-BY-SA** (although I didn't bother to put the CC logos everywhere) and the **Hardware** under the **CERN-OHL-W-V2**. Kind of the GNU GPL equivalents. Both can be found at the **Licenses folder**.

Also, everything used in this project is open-source/free software so anyone could have full access to all files. For the CAD, it was used **FreeCAD**, for the Documentation the **LibreOffice** package.

# About me
At the moment I'm a Electrical Engineering with Electronics Emphasis student at São Carlos School of Engineering at University of São Paulo ([EESC-USP](https://eesc.usp.br/en/)), member of the Warthog Robotics (WR) team with 5.5 years of experience in mobile robotics and in this project I also intend to share some of my maintenance, design, research and competition experience to help you make your project decisions. You can check my [Linkedin Profile](https://www.linkedin.com/in/igorsantabarbara/) or reach me here on GitHub.

# Why another SSL robot?
It's been a while all SSL teams around the world use the same-ish robot, agree on most of the design decisions and there's little to explore specially when it comes to Hardware Design. Even though, I decided to make my own version for two reasons:
1. Most of the designs come from teams with ***very generous*** sponsorships and budgets but that's not the reality undergraduate students (specially in "developing" countries) or even hobbists who are willing to take the challenge face. So the first point is to **provide a design that can be taken completely, as a template or modified** to fulfill the needs of your project, explaining my design decisions and making it more or less a "how to make you own SSL robot" guide. That's because although the League forces the teams to contribute their breakthroughs via a document called Team Description Paper (TDP), the information is still sparse and sometimes not well described/documented.
2. In my experience, I'd say it's quite easy to be an engineer with nearly infinite budget. When you can get electronic components from Digikey or Mouser in less than a week, use carbon fiber everywhere you want or some fancy 3D printing/thousand-axis CNC machining, designing hardware is a trivial ~~if not boring~~ task. With all that put, the other point is to **incentivise or inspire more people and organizations to join the field of mobile robotics or to step up their game**.

# Repository Organization
I'm borrowing the project file system we use at WR because I think it's well suited to organize this kind of project:
- DOC - stands for "Documentation"; self-explanatory.
- DST - stands for "Distribution"; it contains the results/products/outcomes of the source files. Basically what you'd need to manufacture the robot, for example, 2D drawings for machined parts, .steps to make your own G-Code, etc. 
- SRC - stands for "Source"; it contains CAD files, mainly.

Besides, there'll be a README.md file everywhere I find interesting to explain a design decision, tell about my experience on a subject or explain/give the background on a point.

Also, I'm going to use a V-Model to organize the development but don't expect an Aerospace-grade Systems Engineering. I'll keep things way simpler just to use the model more on the mindset side of the things instead of really going deep in each step and validation.
<img src="https://user-images.githubusercontent.com/38017504/129079031-009f0c9a-4be0-4add-80eb-8f2cd120da57.png">
So, basically this V-Model-thing it's more about how/where the project starts and ends. With that put, I suggest going first to the Documentation (but of course, if you're not interested, you can just go right to the CAD files or something else).
