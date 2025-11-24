# Marketing: gamedev: consoles

## Setting Boundaries, Open Source, & Gamedev on Consoles

https://www.fortressofdoors.com/setting-boundaries-open-source-gamedev-on-consoles/

### Some cautious words about console development

A lot of people are interested in consoles because:

- They're struggling on Steam
- Consoles seem less crowded
- Consoles are wrapped in an aura of mystery and prestige
- They want to fulfill the childhood dream of shipping a "real" console game

The truth is that console development is extremely difficult, and the technical challenges -- which are significantly higher than on PC -- are honestly the least of your concerns.

You shouldn't expect console platform hholders to be super excited about late ports of an indie game, particularly multi-platform ones.

You will need to pay for kits, and you will need to get through official console QA certification. You will almost certainly fail the first time, and probably a few times after that. QA is expensive and time consuming not just because of the stringent requirements, but also because of all the extra stuff you have to implement to pass, which includes a lot of weird platform-specific features. You can pay for professional QA to speed things up.

The worst part is you can't google this stuff, you have to either seek support from the console holder or hope someone on their private forum that's also under NDA can help you out.

Developing for multiple consoles at once - don't do it. Just don't. Take one thing at a time. Doing multiple consoles simultaneously multiplies all of the above challenges by ten. I developed for three consoles simultaneously (four technically, but we gave up on the WiiU). Big studios will have a separate build machine for each console, not to mention entire separate porting teams, whereas I was plugging them all into my one PC, and trying to sort it out in parallel with James Gray, my long-suffering console porting engineer who had his own kits. And each platform all wanted different versions of compiler software and all had their own cables and controllers, and they didn't all play nicely together, and everything was a tangled mess both virtually and literally, and if I sneezed everything would break and it would take me all day to get everything straight again just to be able to compile something