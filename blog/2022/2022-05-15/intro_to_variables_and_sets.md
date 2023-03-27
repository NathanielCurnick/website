<!-- html -->
<!-- wp:paragraph -->

<h1>Introduction to Variables and Sets</h1>

<p>In the last article, we assigned truth values to statements. However, if these statements depend on variables, it can
    be less obvious what the truth value is. For example, it is very easy to assign a truth value to the statement "3 is
    a prime number", but what about the statement "x is a prime number"? In this instance, we might change the statement
    from \(P\) to \(P(x)\) to stress we are talking about a variable.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>The variables x do not have to be numbers - they could be anything. Mathematicians obviously use numbers the most,
    but since logic is totally universal, this could be countries, people, plants, animals and absolutely anything at
    all.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Let's try and convert some English statements into logical statements. Let's begin with "x is a prime number, and
    either y or z is divisible by x". If we make \(P(x)\) stand for "x is a prime number" and \(D(j, x)\) mean "j is divisible by
    x" then the whole statement can become "\(P(x) \text{ and } (D(y,x) \text{ or } (D(z,x))\). Notice how I define \(D(j,x)\) - \(j\) here is a dummy
    variable to which I will soon replace with my real variables. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>So, how do we assign truth to such statements? "x is a prime number" is true when \(x = 3\), but false when \(x = 4\). We
    remedy this by the creation of sets. A set is simply a collection of any objects, and we use curly brackets to
    collect them together. For example, the set \(\{0,1,2,3,4,5,...\}\) is often known as the natural numbers (some authors do
    not include the 0). Once the pattern has been established we use the "..." notion to mean "and so on", usually
    implying this set is infinite. Now that we are armed with the set, we can create truth sets to assign truth to
    statements involving variables.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>But how do we create truth sets? Short of writing out the whole set, there is a "hack". We can construct the set
    using a logical argument itself. Consider the set \(\{2,4,6,8,...\}\). We could also write this as \(\{x | x \text{ is an positive
    even integer } \}\). This leads us to the concept of free and bound variables. Let's suppose a statement like "\(y\) is a
    member of \(\{x | x \text{ is a prime number } \}\)". We know \(y\) is prime, but we do not know which one - but it is one of them. \(x\)
    however in this statement is free - it will always range over all of the possible prime numbers. It is simply a
    dummy variable that we use for convenience.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Perhaps you can see how this helps us. Consider again "\(x\) is a prime number". This statement is true for some values
    and false for others. We can figure out which ones by creating a truth set \(\{x | x \text{ is a prime number }\}\) to tell us
    which ones. This is a rather trivial example, but let's consider the statement "\(x\) is an even prime number". What is
    the truth set of this statement? Since there is only one even prime number, we can write it out as \(\{2\}\). Note how
    this is not the same thing as 2. 2 is a number, \(\{2\}\) is a set containing only one number. Logically, they are not the
    same thing. Programmers might understand the first as an integer type and the second as an array of integers with
    only one integer. </p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Let's try a few examples to solidify these concepts. Consider the set {Alberta, British Columbia, Manitoba, New
    Brunswick, Newfoundland and Labrador, Northwest Territories, Nova Scotia, Nunavut, Ontario, Prince Edward Island},
    what would be its definition? We would write \(\{x | x \text{ is a State of Canada } \}\).</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>As a final example, let's define a set - the reals. The real numbers are positive and negative rational numbers. This
    includes integers like 1, 5, -2, 0 and so on, but also positive and negative fractional numbers like 0.25, 0.7896
    and -0.111102. Consider the set definition \(\{x \text{ is a member of the reals } | 2x^2 + x - 1 = 0 \}\). I won't go into details
    on solving quadratics, but we find that \(2x^2 + x - 1 = 0\) has solutions -1 and 0.5. Both of these are reals, so the
    truth set is \(\{-1, 0.5\}\).</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>I hope this very short introduction to truth sets and variables in logical statements has given you an idea as to the
    foundation of the system. Really there is much more to say, so tune in next time for more details on sets!</p>
<!-- /wp:paragraph -->
<!-- html -->