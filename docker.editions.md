OK I want to get you right into Docker.

Before we get to Docker, we got to actually have Docker. We've got to install
it; and in order to install it,

you

you need to know which edition you need to put on your machine.

We're going to go through that real quick.

Basically, there's a dozen or more editions of Docker now.

Those are different "flavors," basically, for different operating systems. We
need to go through

real quick in this lecture, and in the few lectures after it, which one you're
going to use for the course.

You figure out which one that's going to be. You jump to the lecture that will
set you

up and install it, and then configure it properly for this course.

We also learn real quick about the difference between the free Community Edition
Docker, that's Docker

CE, and then the EE version, the Enterprise Edition. We won't actually cover
much of that in this course.

It's a paid version and it's usually for larger business, but we'll touch on it
every so often but you

won't be using it in this course.

We're going to use totally free software. You're also going to learn real quick
what Stable and Edge

are, how the releases are done, and which versions you should use.

We've got to get you figured out to which one you're going to use and how

you're going to use it.

Do realize that Docker is not just a simple point and click installation
sometimes because it's

actually a much bigger product than it was four years ago.

They've added a whole bunch of features that manage and solve a whole bunch of
problems.

So do realize that sometimes it seems a little more to install it than what is
necessary because it's

now such a bigger thing than a container runtime.

It also moves really fast.

The

container ecosystem is red hot, with innovation on a yearly basis.

It's sometimes even hard to keep up when you're in the industry.

Do realize that your version matters and you need to make sure that you're on
the most recent version.

If you follow the directions at the store, or if you follow my videos here,
we'll get you there.

Docker CE is the version we're going to focus on on this course.

That is the free open source toolkit that is full of features and can get you
from dev all the way through

to production.

There is another version called Docker EE, or Enterprise Edition, and we'll get
to that in a second.

There are three major types.

I like to break down the different editions, of which there is now over a dozen,
into

three major types of installs.

The first one is, you're just installing it directly on a supported operating
system; meaning that it

runs on that kernel and that OS and it's supported. Mostly until 2016,

it was really just Linux.

Then we started seeing innovations where the Raspberry Pi could use it, and we
saw it on mainframes

and other Linux variants or Unix variants started to use it.

And then Windows Server 2016 supported it natively.

So that's pretty exciting on the Windows side.

But that's the direct method. On Mac and Windows 10,

I would call this, not the direct method, but more of a suite of tools including
a GUI and settings

preferences, to make it really easy for you to develop Linux containers, or now

Windows containers, on either one of those operating systems. Because the Mac
natively doesn't support Docker.

So what has to happen in the background on the Mac, and also for Windows 10, is
a small virtual machine

has to be started by Docker to run the containers in. It's transparent to you

most of the time. You're never going to know it's there. But that is part of
those editions.

So they are a little bit different. The last option is the cloud. The cloud is
really

what I would say are AWS, Azure, or Google versions.

So Docker for AWS, for example. Those versions come with Docker installed on
Linux usually, but they also

come with features specific to that cloud vendor.

So on the AWS side, it'll come with the cloud formation template, it'll come
with persistent storage

options for storing your databases.

It will come with features that automatically update elastic load balancers and
all those things that

you would care about if you were in AWS.

The same can be said for Azure and pretty soon Google Cloud, once it graduates
from Beta.

Those three different types of installs all come together to support

a full life cycle of Docker options. In this course, we're really going to be
focusing mostly on

Docker for Mac, Docker for Windows, and installing Linux locally

if you're on a Linux machine, for local development and testing. At the end, we
will start to create Swarms in the cloud,

and then I'll give you options at that point on how to do that.

A real quick note on the differences between CE and EE, and Stable vs. Edge.

We mentioned that the Docker version we're really using, or the edition

we're going to be using, is Docker Community Edition. That's CE; that's the free

open source version.

The other version Docker EE, is Docker Enterprise Edition. It's a paid version
that you pay per node.

It's not necessarily ideal for the independent developer or the single person,
it's really better

for larger organizations that have lots of servers they need to run; and, they
need maybe management GUI

or LDAP authentication for active directory, or maybe they just need 24/7 phone
support.

You can buy that on a monthly or a yearly subscription.

And you do get a lot for it.

They certify that EE version so it's specific versions of Linux and Windows.
Then the Docker CE

has a broader support where they generally test it a little bit on a bigger set
of platforms.

You'll see all of those at the store when you go to download it.

If you're curious about the pricing of the Enterprise Edition, you can go to
docker.com/pricing.

Again, we're not going to discuss a whole lot about that in this course. We will
mention it a few times,

but you can check that out.

And one last thing real quick, we just want to discuss the difference between
the support life cycle

and the versioning of CE, EE, and what Stable vs. Edge means.

Edge actually means beta in the Docker world. It comes out every month.

Unfortunately it's only supported for a month until the next beta comes out.

I personally run Edge on my laptop because I like to test new Docker things. You
may not want to do that.

When you're downloading Docker by default, you will get the Stable version that
comes out once

a quarter.

You'll also notice that it actually looks like it's supported for four months on
the Stable version

because it kind of gives you that one month to actually install the next
quarterly stable update before

they stop updating the previous one.

Of course if you want to pay for EE, you get longer support life cycles and
patches for whatever version

you decide to install.