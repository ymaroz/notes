# Animation Library Comparison

- [The case for an animation library](#The-case-for-an-animation-library)
  - [Springs vs Tweens](#Springs-vs-Tweens)
- [Potential dependency libraries](#Potential-dependency-libraries)
  - [framer-motion](#framer-motion)
  - [react-spring](#react-spring)
  - [gsap](#gsap)
  - [react-transition-group](#react-transition-group)
  - [Opinion](#Opinion)

## The case for an animation library

I believe it would be beneficial to create a library of reusable and consistent animated wrappers to be distributed by the q-components-react library. I am proposing creating several common animation patterns (slide, fade, collapse, translate, rotate) that can be used to build subsequent sharable components or ad-hoc animations of larger components or between pages; if successful/useful we can also build more complex patterns (draggable items/lists, layout transitions). Abstracting the patterns themselves will provide several advantages: we can retain an additional level of control on the animations (limiting ranges/durations, disabling animations, unified/consistent animations); allow for more dynamic/fluid UI components; and, assuming we are basing our library on a dependency, we can replace a portion or the entirety of said dependency without effecting any of the components using our wrappers, should the need ever arise.

### Springs vs Tweens

Animations can typically be generalized into two categories: spring or duration based. You will frequently see both types described as “physics based”. Duration based animation is the more traditional approach- an animation begins, it takes x milliseconds for an element to move from point A to point B and then the animation is finished (the combination of the duration and movement is frequently referred to as a tween). Spring based animation seems to be a newer approach where a designer/developer defines point A and point B and configures a spring to apply to the element; the configuration will define things like elasticity or clamping and the animation will still begin at A and end at B. The configuration informs the element how “elastic” the end point of B should be (or if it should clamp), so that the element could “spring” past the terminus before finally settling, or perhaps have some inertia as the animation begins. This usually makes for a more dynamic and visually pleasing animation. Duration based animation can also accomplish this springy-ness with things like easing or delays. Spring based animations can also typically set some kind of duration as well; so in general there’s a fair amount of crossover between patterns. react-spring makes a more detailed case for spring animations [in its README](https://github.com/pmndrs/react-spring#why-springs-and-not-durations).

## Potential dependency libraries

### framer-motion

- ~ 200k weekly downloads

- MIT License

- < 200 open issues

- ~ 2mb uncompressed

- [Examples](https://www.framer.com/api/motion/examples/)

framer-motion is a hybrid (spring or timing) animation library for React components published and maintained by Framer. Framer’s major product is a design/prototyping tool called Framer that can be used for free or for an annual fee. They released their motion API at the beginning of 2019 and it has seen an increasing adoption rate since then (10x in the last year). The original motivation for the API was to allow easy handoff between the prototyping tool and React components; the idea being that a designer/developer can prototype the animation in Framer and then pass the same configuration into framer-motion. Additionally framer-motion has a major focus on improving features and developer experience. The library offers several desirable features “out of the box”: gesture support (hover, tap, pan, drag), shared layout animations, animating mounting/unmounting components, easy coordination of multiple/separate animations and several powerful hooks to tie into things like viewport/element scroll, motion values that don’t trigger re-renders, and springs/transforms.

### react-spring

- ~ 450k weekly downloads

- MIT License

- < 150 open issues

- ~ 1.3mb uncompressed

- [Examples](https://www.react-spring.io/docs/hooks/examples)

react-spring is a spring based animation library for React components. It has been around since early 2018 and gained a large adoption rate, spiking even further after endorsements from members of the core React team. It is entirely open source and community supported. Additionally there are several projects maintained by the original author/maintainer that either extend react-spring or extend the complexity of the API (most notably extending/forking three.js to enable 3D animations).

### gsap

- < 200k weekly downloads

- Business/Enterprise licensing

- 5 open issues

- ~ 2.3mb uncompressed

- [Examples](https://codepen.io/GreenSock/collections/)

gsap is a javascript animation library focused on complex custom animations. It is framework agnostic and has been around longer than any of the other listed libraries (I believe ~15 years in one form or another). There is a very fairly active community and tons of beautiful examples. It is a timing/duration based library using “tweens” and “easing” and is extended by a number of plugins (text animation, draggable, etc). The offer several licensing agreements, \$150/yr for Business; they mention several other options, but I haven’t received information about the “lifetime” Business and Enterprise (seems to also be yearly or lifetime) level agreements. Additionally there are packages like react-gsap that turn animations into wrapper-components that we likely could use as a model to build something similar internally.

### react-transition-group

- ~ 6mil weekly downloads

- BSD-3-Clause License

- ~ 100 open issues

- ~ 250kb uncompressed

- [Examples](https://codesandbox.io/examples/package/react-transition-group)

react-transition-group is a timing based animation library for React components. It has been in use since the end of 2016 and is mentioned in the official React docs as the example of animating components. It often prioritizes CSS transitions over animating with JS. It has a significantly larger user base than other libraries. While it can now be used with hooks, it often relies on the renderProps pattern as well.

### Opinion

I have personally/professionally worked with react-spring, react-transition-group, and framer-motion. I believe that framer-motion is the best option currently available. It provides the happiest developer experience, offering more features, an easy to learn API, easy designer to developer handoff, and strong community support. Their major releases have tended to be more iterative and less breaking. react-spring is another excellent option with a similarly active community and a fairly straightforward API. However, I’ve run into issues in the past where they are more concerned with building future versions than fixing outstanding problems in current releases. Their v9 release has been in development for at least a year and still doesn’t seem ready to release (it will also contain major breaking changes). I also feel framer’s API is a little easier to learn: spring relies on learning 4-5 hooks for simple animations, where motion just relies on the motion export to get started. gsap seems like an interesting option, and seems to be the most flexible and consistent, as it’s not tied to any framework. It also offers a prototyping tool for design to develop handoffs (with a paid license). Simple animations aren’t too difficult to write or understand, but things seem to get exceedingly complex rather quickly, so the learning curve seems a bit steeper. It also relies on plugins for extensibility. react-transition-group is really not preferable in my opinion. It is fairly dated and community help/examples tend to be dated as well (hooks are available in v2, but they often use old patterns like class components or renderProps pattern). I’m honestly quite surprised the user base for rtg is so high. The API is super simple offering a total of 4 exports, meaning the customization and complexity must come from our own development. For example it does not provide any simple way to handle things like gesture support or scrolling hooks.
