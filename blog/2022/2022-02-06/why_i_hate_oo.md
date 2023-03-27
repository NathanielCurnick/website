<!-- html -->

<h1>Why I Hate Object Orientated Programming And What to Use Instead</h1>

        <!-- wp:paragraph -->
        <p>Anyone who has began programming over the last few decades has probably been extensively exposed to the concept of
            "object orientated programming" (I'll refer to it as OO from now on). In fact, most courses in programming or
            programming textbooks say that OO programming is the correct way to program.</p>
        <!-- /wp:paragraph -->
        
        <!-- wp:paragraph -->
        <p>Indeed, let's look at a few examples…</p>
        <!-- /wp:paragraph -->
        
        <!-- wp:paragraph -->
        <p>In Head First Python they say</p>
        <!-- /wp:paragraph -->
        
        <!-- wp:quote -->
        <blockquote class="wp-block-quote">
            <!-- wp:paragraph -->
            <p>Get ready to take a trip to a foreign country. It’s time to visit Objectville, a land where objects do just what
                they’re supposed to, applications are all well-encapsulated (you’ll find out exactly what that means shortly),
                and designs are easy to reuse and extend. But before we can get going, there are a couple of things you need to
                know first, and a few language skills you’re going to have to learn. Don’t worry, though, it won’t take long,
                and before you know it, you’ll be speaking the language of OO like you’ve been living in the well-designed areas
                of Objectville for years.</p>
            <!-- /wp:paragraph -->
        </blockquote>
        <!-- /wp:quote -->
        
        <!-- wp:paragraph -->
        <p>Of course, I'm not in the object orientated crowd, but so are a growing number of people. In the second edition of
            the book they instead say</p>
        <!-- /wp:paragraph -->
        
        <!-- wp:quote -->
        <blockquote class="wp-block-quote">
            <!-- wp:paragraph -->
            <p>Q: Exactly what type of programming language is Python: object-oriented, functional, or procedural? A: That’s a
                great question, which many programmers moving to Python eventually ask. The answer is that Python supports
                programming paradigms borrowed from all three of these popular approaches, and Python encourages programmers to
                mix and match as needed. This concept can be hard to get your head around, especially if you come from the
                perspective where all the code you write has to be in a class that you instantiate objects from (as in other
                programming languages like, for instance, Java). Our advice is not to let this worry you: create code in
                whatever paradigm you’re comfortable with, but don’t discount the others simply because—as approaches—they
                appear alien to you.</p>
            <!-- /wp:paragraph -->
        </blockquote>
        <!-- /wp:quote -->
        
        <!-- wp:paragraph -->
        <p>So indeed the popularity and the universalism of OO style has fallen over the last few years. That second edition was
            published in 2016, and things have only gone downhill for OO since then. This article might be a little on the
            longer side, so I'll break it down into nice sections. First, I want to go over what I am NOT complaining about.
            Then, I will discuss what I AM complaining about, and why this makes OO bad. We'll have a look at why OO is so
            popular if it is bad. Then take a more detailed tour of why OO does not work. Finally, we can wrap up by producing a
            sketch of how we should program instead.</p>
        <!-- /wp:paragraph -->
        
        <!-- wp:heading {"level":1} -->
        <h2 id="what-i-am-not-complaining-about">What I am NOT complaining about</h2>
        <!-- /wp:heading -->
        
        <!-- wp:paragraph -->
        <p>So quickly before I move on, what am I not arguing against? I am not arguing against classes. Sometimes the explicit
            association between types and methods is a good idea. This is what we use structs for in Rust. For example, I might
            have a Vector struct and I explicitly associate a function (we call this an implementation) to get the magnitude of
            that vector. We still, however, allow for the capacity to not do this. While we're on the subject of structs, they
            really are close to a class in many ways. Except they don't have inheritance, but since inheritance is discouraged
            now in object oriented code anyway, the occasional benefits of a class can easily be satisfied by a struct. As an
            example my final year C++ exam was to make a program a simulation of a disease spreading in a population. The
            "people" in this simulation had certain properties like alive/dead, infected/healthy, immune and so on. You could
            create a person class here and have a vector of person instances, but I would argue this isn't exactly object
            orientated code, since it could just as well be done with a struct. Anyway, the point here is occasionally, yes, we
            do want to associate data and we do want to associate methods with that data but that does not require a
            top-to-bottom design approach. As I want to make very clear (and I have the sneaking suspicion that many will not
            understand this) my issue is not with classes/objects in isolation but with the top to bottom design approach.</p>
        <!-- /wp:paragraph -->
        
        <!-- wp:paragraph -->
        <p>I am also not arguing against inheritance. Even among the object orientated hold outs, inheritance has become
            somewhat unpopular. Therefore, it simply isn't pertinent to the discussion, as object orientated code without
            inheritance is still bad. Most OO design these days recommends using composition rather than inheritance, which is
            suspiciously how structs work. I am also not arguing against polymorphism. Polymorphism is a perfectly fine idea,
            and sometimes polymorphism is possible in greater degrees in procedural code than object orientated code. Although,
            I will say that since object orientated code is dysgenic in nature, it makes polymorphism seem awful – it isn't the
            polymorphism that's unattractive here though, but something else entirely (OO).</p>
        <!-- /wp:paragraph -->
        
        <!-- wp:heading {"level":1} -->
        <h2 id="what-i-am-complaining-about">What I AM complaining about</h2>
        <!-- /wp:heading -->
        
        <!-- wp:paragraph -->
        <p>Whenever I say "I hate object orientated code and think it should never be used" generally the reaction I get is
            "wait, how can you not like object orientated code? It makes code easy to read, modular and reusable!". I simply ask
            them "which style of programming explicitly wants to make code hard to read, unmodular and impossible to reuse?"; I
            have yet to get a good answer to this question. I understand what the goals of OO are, and every paradigm shares
            these goals. The question is: how well does the paradigm actually achieve this?</p>
        <!-- /wp:paragraph -->
        
        <!-- wp:paragraph -->
        <p>In the early days of programming all programs were procedural and imperative. Procedural meaning that there are no
            explicit associations between data and behaviours. Imperative means we can mutate state on the fly whenever we feel
            like it. This is really the default and most obvious way to get work done. At this point there wasn't really a name
            for this style – if you asked someone what "style" of programming they used they would probably answer something
            like "we just program". As programs became larger, started to have way more state, and multithreadding is introduced
            this mutation on the fly becomes problematic to keep track of. So procedural and functional code is born, functional
            meaning that we try and shed as much state as possible by creating as many logic functions as possible that know
            nothing about the state – they take in some inputs and return some outputs. A different approach is object
            orientated and imperative. The OO means we will be slicing the problem down into small pieces of segregated state in
            a divide and conquer style.</p>
        <!-- /wp:paragraph -->
        
        <!-- wp:paragraph -->
        <p>This is what I complain about: encapsulation. Let me say this very clearly: encapsulation does not work on a fine
            grain level.</p>
        <!-- /wp:paragraph -->
        
        <!-- wp:heading {"level":1} -->
        <h2 id="why-is-oo-so-popular">Why is OO so popular?</h2>
        <!-- /wp:heading -->
        
        <!-- wp:paragraph -->
        <p>Why did OO become so popular? I think Richard Feldman lays out a good case in his talk "Why Isn't Functional
            Programming the Norm?". He argues that it's, more or less, a coincidence. To some extent he's right, although I
            think he misses something about Java. Java is pretty much the reason that OO is so popular. Java came at a time when
            development was very difficult. In the early 90s to develop you we're probably writing in C or C++ and then had to
            turn this into an actual Microsoft Windows application by using Win32, which was this super macro-heavy monstrosity
            and challenging to use. Especially since what was taught at universities was almost invariably the more "pure" form
            of programming (I mean C or C++ on their own). Plus larger programs had to have dependencies managed manually which
            usually meant loads of header files and linker nightmares. Java solved pretty much all of these problems. No header
            files. What you learned from a textbook is what you actually programmed. Write once and use anywhere. This must have
            been a breath of fresh air. At the time too, the dangers of OO were not understood. Also, somehow, there was cash
            for massive marketing campaigns aimed at developers to use Java. I'm not sure another language will ever get
            advertised like that. At any rate, once people start to do things, it can become hard to divert that. Social inertia
            is powerful. "We do it this way because we always have" may not be a logical argument but it is a powerful one.</p>
        <!-- /wp:paragraph -->
        
        <!-- wp:heading {"level":1} -->
        <h2 id="why-oo-is-terrible">Why OO is terrible</h2>
        <!-- /wp:heading -->
        
        <!-- wp:paragraph -->
        <p>The other thing about object orientated programming that is easy to notice is how much extra baggage it holds around
            the edges. Object orientated programmers constantly try and come up with new ways to deal with the fact that OO
            simply doesn't work. I'm thinking of things like test driven development, behaviour driven development, agile
            development, extreme programming, patterns, SOLID. All of these things simply feel like nuisances that distract from
            the real task at hand, that is, creating logical systems that solve specific problems. In other words, these are
            band aids to deal with the fact that OO simply doesn't work. It's as though every few years people say "hey
            programming would be great if only we did this"… "ok THIS time we've cracked it". Madness. Also, before anyone says,
            I am not against tests. Tests are not the same thing as test driven development. I'll get into this later but Rust
            has a great testing system.</p>
        <!-- /wp:paragraph -->
        
        <!-- wp:paragraph -->
        <p>Explicit and forced associations between data and functions comes with a problem. Notice how I say forced. An object
            itself is a wrapper for two kinds of things, some state code and some logic code. The state code is hidden behind
            some public functions.</p>
        <!-- /wp:paragraph -->
        
        <!-- wp:paragraph -->
        <p>Now, the idea behind encapsulation is top down. We have a strict hierarchy where there is some top God object which
            contains sub-objects, and those sub-objects contain sub-sub-objects. The POINT is that the God object can not
            directly talk to the sub-sub-objects, only the sub-objects. Now, if you are a defender of OO reading this and
            thinking "but that's not how anyone programs in OO" then you would be right. Most people who program this eventually
            realise that that objects <em>only</em> talking to those directly above and below them is not going to work, so all
            kinds of cross-network links are made. When you do this, however, encapsulation goes out the window. It begs the
            question: <em>why did you bother in the first place?</em></p>
        <!-- /wp:paragraph -->
        
        <!-- wp:paragraph -->
        <p>The problems of OO, then, are more human than they are scientific. I can see this working. In theory. But in reality,
            someone has to program this. In reality for some giant project someone has to first work out, top down, precisely
            the structure of the code and this can never change. This is <em>hard.</em> Hell, for really huge projects being
            worked on by multiple people, I would say this is impossible for all intents and purposes.</p>
        <!-- /wp:paragraph -->
        
        <!-- wp:paragraph -->
        <p>The issue with OO is that it requires you to work out things about your code on the fly that are really very hard
            questions. Making good and useful abstractions on the fly is impossible. It takes years for really good APIs and
            modules to develop that are flexible and useful and self-contained. The idea that the average developer, under all
            the time pressure that usually comes with the job, could do this constantly, every day, seems ludicrous. Programs
            usually grow in complexity and change in design over time – I think a style that is very compatible with this bottom
            up approach is much better.</p>
        <!-- /wp:paragraph -->
        
        <!-- wp:paragraph -->
        <p>A lot of people think I am anti-abstraction, but this isn't really the case. I think abstraction is good, but I think
            no abstraction is better than bad abstraction. A bad abstraction can be, well, abstract in the other sense of the
            word. Difficult to understand. Most OO projects quickly end up a total mess where finding where anything actually
            <em>happens</em> becomes and impossibility and methods and objects do not do what the name suggests they should. In
            other words, the flow of logic becomes very muddy and obscure. Programming is all about logic flows, so when these
            break down, it is pretty catastrophic. In the same way, no structure is better than bad structure. Imposing a
            top-down structure on our code which doesn't pan out in the long run is so much worse than allowing the natural, and
            probably "correct" structure to "evolve" in time.</p>
        <!-- /wp:paragraph -->
        
        <!-- wp:paragraph -->
        <p>While we're on the topic of abstraction, I think OO has corrupted what it means. Abstraction originally in
            programming referred to abstract data types. For example, we can define a stack entirely in terms of how we interact
            with it and never mention the kind of data that goes into it. Therefore, we can put anything into it. This is a
            great idea. Then abstract came to mean something like simplifying complexity. Finally, abstract seems to be a way
            programmers say "I don't need to know how my code works". We really ought to know what our code is doing all the
            time, perhaps except when a package someone else has used (but I <em>hope</em> they know what that code does!).</p>
        <!-- /wp:paragraph -->
        
        <!-- wp:paragraph -->
        <p>There are really two kinds of code. State code and logic code. I think the names of these give you a really good idea
            of what they do. The functional approach is to try and shed as much state code as possible and convert it into logic
            code. The object orientated approach is to slice the state code up into small pieces and wrap that into objects. The
            state code can not directly be interacted except by the use of public facing methods. What if you have too much
            logic or too much state? Seriously, what happens if you have logic functions left over that it doesn't make sense to
            combine explicitly with a data type? This is surprisingly common. Almost every object orientated project I have ever
            come across ends up having some sort of utility object that just contains an assorted pick-a-mix of random methods.
            Object orientated gurus would say this is bad design and the structure should be totally redesigned to avoid this –
            but I think the fact it can happen and the fact it is so easy to happen is the most brutal destruction of the idea
            possible. It simply fails under its own weight. What if we go to the other extreme? More state than we have methods
            to associate with? We end up with some random state object which just contains a selection of variables and then
            that comes with 50 lines of boiler code just to interact.</p>
        <!-- /wp:paragraph -->
        
        <!-- wp:heading {"level":1} -->
        <h2 id="what-should-we-use-instead">What should we use instead?</h2>
        <!-- /wp:heading -->
        
        <!-- wp:paragraph -->
        <p>So, what's the alternative? Functional programming! Or at least procedural programming in general. Rust is a great
            option now – explicitly anti-object orientated. Rust has lots of useful features, like guaranteed memory safety, and
            the environment is a joy to work with. Cargo is one of the best tools I have had the pleasure of using.</p>
        <!-- /wp:paragraph -->
        
        <!-- wp:paragraph -->
        <p>Encapsulation at a larger scale can be a good idea. A module fills the roll perfectly. I have some complex code which
            is hidden behind a few simpler public functions that take some data and return some result. I have just fulfilled
            the goal of object orientated code in a much cleaner way in fact. Now, rather than needing to initialise a bunch of
            objects in my code I simply call public module functions when convenient. Modules, by the way, are logic code. I'll
            often create modules for myself just to push away self contained pieces of code from the main logic flow of the
            program.</p>
        <!-- /wp:paragraph -->
        
        <!-- wp:paragraph -->
        <p>Functional code also allows for the reduction of state code, which means looking at state code becomes very easy to
            understand. This is very beneficial, since all one needs to worry about in terms of logic is inputs and outputs.
            Functional code, with its immutability, also tends to be very easy to multithread and optimise. I think that the
            popularity of functional styles of programming will mean that languages like Rust will explode over the next few
            years.</p>
        <!-- /wp:paragraph -->
<!-- html -->