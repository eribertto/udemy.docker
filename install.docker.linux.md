Are you using Linux as your main operating system on your laptop or desktop? Or
maybe you just want

to install Docker and use it on a Linux server in the cloud or in a Linux VM?

Then this is the video for you.

We're going to go through all the Linux features that you need to make sure are
set up correctly so

that you can get through this course. And do all of the examples and code stuff.

So first off, congratulations! If you're going to use Linux,

it's actually the easiest to get started with Docker. Docker was made for Linux.

It now actually has Docker Containers for Windows.

But we're going to get to that later in the course.

But most of this course is all about containers on Linux.

And so when you think of the Mac and the Windows stuff, it's mostly them
actually running a tiny little

Linux VM in the background. For you, if you're going to be running natively on
Linux, you're good

to go.

There is no emulation or little VM running in the background; it just runs
straight on your operating

system.

So there's 3 main ways to get Docker on Linux and it might not be what you
expect.

The first one is through a script that's actually using a cURL script.

It's actually my preferred way. Especially when I'm installing it from just for
testing or playing around

with it, because it does use the Edge releases, which are not the Stable sort of
production-y version.

They're more of the beta monthly releases.

So obviously you don't want to do that for maybe a production system where you
want to automate over

and over again for creating servers in the cloud or your data center. But for
installing locally, I highly

recommend just using Edge.

It's actually quite Stable for being beta.

I usually don't have any issues with it and but it allows you to test out
features quicker because it

comes out monthly.

So that script would actually get you installed.

And we're going to be using that script today.

I'm also going to show you though about the store, which has specific
instructions for each distribution.

So whether you're on Ubuntu or Debian or Red Hat or CentOS, or just like all of
the different distributions

there.

They largely come down to Debian-based distributions or Fedora- and Red
Hat-based distributions and the

YUM package manager and the APT Package Manager right.

So there are other variants and other things out there but, really in this
course, for Linux, we're really

just mostly talking about those two because they cover 95% of the use cases in
Linux. You

need to go to the store to get the specific instructions for your distribution.
Because you'll learn

that you shouldn't be using the built-in default one that might come with your
package manager.

We'll talk about that in a second.

I want to note real quick though, if you're on Red Hat Enterprise Linux -- or
RHEL, as I'll call it from

now on -- that only really officially supports Docker Enterprise Edition, which
is the paid version.

Docker's attitude really is, a paid operating system gets a paid version of
Docker. A free operating system.

gets a free version of Docker.

Now we're talking about the native stuff like Linux, right.

In this case, if you're going to be on Red Hat, you can actually go to the store
and look up the CentOS

version because it's also a YUM package manager version and you can do that
Docker CE instead of having

to go pay for Docker EE.

But I just want to tell you that now because if you go to the store and then you
go to click on Docker CE,

and then you go look for Red Hat Enterprise Linux,

it's not going to be there because it's over on the EE side.

Docker assumes if you're running the paid RHEL, that you would actually be
paying for Docker support just

like you pay for your Linux support.

So next up you can install this on any Linux option, whether that's the native
computer on your laptop

or desktop with a GUI or it's a server in the cloud.

All these processes are the same and we will, if there's ever an exception, I
will mention at that time.

This is not going to work for all distributions. Remember how I said 95 is
really 95% is really what

we're going for.

So that's just an estimate of my experience with the people I work with, I have
no scientific background

on that 95%.

But, there are distributions out there that may not work or will not work with
Docker. Specifically

those are the less common or vendor-specific distributions like Amazon Linux or
Linode Linux or

a few other ones out there maybe like Google Cloud Linux, which I know is still
beta testing Docker

support.

So Docker is a leading-edge technology that uses the OS kernel and specific
features in that kernel.

Those particular kernels, at least in the past, have not had all the features in
them that Docker needs

to work properly.

So just for this course a lot of my stuff is going to be on my demonstrations
and stuff are going to

be on a Ubuntu or Debian variant.

And actually in this one we're going to use Mint here in a minute.

And lastly don't use the pre-installed setups.

This is generally my recommendation because Docker moves really fast, and you
want the latest version

of Docker, even if you're doing production you want the latest production
version.

When you start out.

If you go to Digital Ocean or AWS or Linode, you might find a Linux install
that's

maybe an easier built in package thing that just says hey we've already got
Docker installed for

you.

Generally I don't recommend using those because you're usually going to get an
old version. You're going to

get an old version of Docker, and then the first thing you're going to have to
do is figure out how to

update it.

And depending on how they installed Docker, it may not be that easy to figure
out how to update it to the

latest edition.

So I always recommend using like the official Ubuntu or the official Fedora or
the official CentOS installs

then manually installing Docker as we will in a minute.

In general this is going to actually go through a couple of basic steps.

We're going to first update our package manager and install Docker. Then we're
going to optionally add

your user account to the Docker group and that will prevent you from having to
use Sudo every single

time you want to run a Docker command, because that can add a little bit of time
and tediousness to

it.

So we're going to do that. Then we're going to go and we're going to clone my
repo from GitHub onto

your Linux machine and then we can talk about getting a code editor if you don't
have one.

And lastly we're going to tweak your terminal and shell set up.

This is a very optional approach but I get a lot of questions in the course from
people saying "hey you're

terminal or your shell did this or looked like this."

"How do you do that?"

So I'm trying to give some information around paths you can go down to maybe
tweak and set up your shell

differently so that it looks more like the one that I use which I use every day
and I customize it constantly

because I'm trying to optimize it.

You don't have to do any of that if you don't want to but I want to give you
some tips on that.

OK so what I have here is a Mint Linux stock, out-of-the-box machine. Mint Linux
is a variant of Ubuntu.

So in case you're curious, it's actually a really great desktop version of
Linux, but I'm sure at this

point you are using your own Linux and you have all the things you want on it.

And so I don't need to tell you about the one that I tend to like.

So if I just type Docker in this scenario it actually says hey it's not
installed you can use APT to

install it and you install with docker.io.

The problem with that is you're going to get an old version maybe even a year
old, which,

that's at least 4 major versions, if not 12 Edge,

minor versions old, so you don't want that you actually want to install it
through the store.

We're going to actually use a script like I mentioned a while ago, but before we
do that, I just

want to show you what it looks like if I go into Docker CE.

I know that basically my Mint is actually just a variant of Ubuntu so I can
scroll down and find the

Ubuntu one.

It actually will step through instructions that tell you which additions and I
know mine is based

on 16.04;

so I click on the Usage Instructions in the top right. And it actually walks me
through it and actually

tells me hey you can use make sure these versions and go get the Docker for

Ubunto from the Docker documentation website; which, is a very detailed,
stepping you through, making

sure that you don't have the old version installed from the default apt-get
repository, and how to

go through each step by step.

However, there is sort of a cheat for this. In our case, we want to install the
Edge release.

I'm just going to go to get.docker.com; and, it's actually going to show me a
script, which I can use

with cURL over https, so that we're making sure that it's officially the script
from Docker, because it's encrypted

on the connection. It will let me install through an automated way; it'll
basically figure out what

is my operating system, what is my kernel, how do I do I use APT package or YUM
package and it will

figure all that stuff out and basically install everything I need.

So I tend to use this because it works so well for local installs.

What I'm going to do is I'm going to copy this, and paste it into my terminal
and it's going to download

the script. And it's telling me just to run the shell, so I put in my admin sudo
password, and away we go.

And you notice while this is installing, that the actual package is docker-ce.
Over the last few

years, as Docker has changed their branding and their versioning and also their
packaging formats, the

name of the actual package that you would install has changed.

The one that it actually installed in the background is called docker-ce,

in case you're curious.

OK.

And it's actually telling us at the end of the install, that if we would like
for our user account to

be able to just run Docker commands without having to type sudo or go in his
actual root, then we can do

this particular command, where we're just adding our user account to the Docker
group on our system.

Then I'm going to need to log out, and back in, in order for that change to take
effect.

So instead of doing that, I just want to test to make sure that Docker's working
and running, and I can

do sudo docker version. OK great. I'll actually log out and log back in in a
minute.

So you don't have to do that part

if you're concerned about security. Here's why. Docker requires root in order to
do the things it

needs to do with the core functionality of Linux. Those things are something
around name spaces and

there's this thing called cgroups and other features of Linux that it needs to
use. So it needs root

for that.

Right.

So when you, by default, when you do things it's going to need to use sudo.

But if you add your user to the Docker group, what you're effectively doing is
giving that user,

in this case Bret, the ability to actually run a Docker container later that
could then have root permissions

on the host.

Now this is a subtle little nuance of security that you don't necessarily have
to worry about if it's

just your local machine.

But there are some variants of Linux that have taken a hard stance on this and
that includes all the

Red Hat.

So the CentOS and the Red Hat Enterprise Linux and maybe the Fedora will not
work with this Docker option.

You will have to either be root or used sudo for every command you use for
Docker on those distributions

of Linux unfortunately.

Again, that's anything based on the Red Hat Enterprise Linux stuff and Fedora
and that's

Fedora, RHEL, and CentOS.

There might be others but those are the ones I definitely know about that won't
work with this.

So in those cases, even if you add yourself to the Docker group, it will do
nothing and you'll still have

to type sudo. You'll know if it doesn't work, because if you just type Docker
version it'll actually

say hey I can't talk to the Linux daemon can you help me out.

And that's because only root can talk to that socket.

That's a hint that you need to be either admin, root rather, or be in a group
that works.

Notice if I do docker version again with the sudo it works.

All right.

Now that you have Docker installed, you're in need to other tools for this
course from Docker. But when

you're using Linux as your main operating system, they don't come bundled with
the install. When you're

on Mac or Windows,

this is all managed for you, but on Linux we have to take things into our own
hands a little bit.

And those two tools are Docker Machine and Docker Compose.

Each one is a single binary, and you can get them on Docker's website in the
documentation area, not on

the store.

And so for the or machine part, I can find here instructions for Linux and I can
just copy that and it

should work on my machine.

Ok and now I can type docker-machine version and make sure that I got the latest
version and it works

and I can do the same thing for Docker Compose... and find that on the
documentation website as well.

And scroll down to the Linux option.

Now, we could actually copy this and install it from here, but I want to show
you an alternative way that

I actually prefer. The nice thing here is that the Docker website has lots of
information about how

to install it.

What it does and what not.

But these are all available on GitHub.

I can go over to github.com/docker/compose and click on the Releases button, and

this is where the official release as you can see the latest is 1.15.0.

In this case, the documentation website is a little outdated with 1.14.0, then
the releases on the

compose an GitHub.

So I just always remember to go check github.com/docker/compose/releases and I
can

do the same thing for machine. And right here, it gives me the information that
I just need to cut and

paste into my terminal.

But you'll notice that I actually got a permission denied error. That's because,
in this case I do

need to be root.

So I'm going to be sudo -i for interactive, and then I'm going to paste that
same information

and then I should be able to back out of root and type docker-compose version.

And there we go.

In case you're curious back over on the GitHub, I can actually just replace that
word compose with machine

and end up right over on the machine page and the releases for docker-machine.

Notice this is on v0.12.2. I can copy this stuff here as well and install it
that way instead of the

documentation website way.

So the choice is up to you.

There's not really much information about installation on GitHub.

The much more information is over on the documentation site for Docker that is
docs.docker.com.

And then one last piece information here is that because we manually installed
these that also means

that Compose and Machine we have to manually update.

So you just need to make it a part of your sort of mental checklist every month
or two, to probably go

check for new versions of Compose and Machine because they do update pretty
frequently.

Hopefully in the future Docker will add packages to the package managers for
these so that we can automatically

update them with the rest of our system just like we do for the Docker install.

OK so let's go get my repo.

Now there's several ways you can do this. One way on GitHub, is that you simply
download their GUI

and use it, but they don't actually have an official one for Linux yet.

So you would need to go get a different third party one.

And we're not going to talk about that.

So we're just going to use the command line.

So if you're looking at my repo page under my GitHub account, you'll find that
link in the Resource

section under Section 1, under the Getting Resources lecture.

And over here you can just copy this you URL and paste it in the command line.

But if you've never used Git before, you won't have that installed.

So if I tried to git, it would not be there so I do need to install

Git real quick.

OK so now I should have the version.

Yep.

OK I got Git installed, and now I'm just going to make a directory real quick,

To put this repo in.

And so I do git clone, and then I paste in that URL that I got from the web
page. And that will pull

down my repo.

Now you could download a zip file of my repo but it does get updated as I fix
things or make things

better.

And so it's easier when you're starting this course, maybe a month later if
you're still doing the course,

that you just need to do

git inside the directory actually...

So inside the udemy-docker-mastery directory I could just do a git pull, and
that would get the latest

updates for the course.

All right.

Next we want to talk about code editors.

I personally like Visual Studio Code.

It's very similar to GitHub's

Atom, if you've ever used that, or Sublime Text, if you've ever used that.
Obviously if you're a Vim fan

or Emacs, or any of the other editors you can use all those.

But I will be showing off a little bit of Visual Studio Code in this course
because it has a really great

Docker add on.

So I'm going to download the Debian version, and on my version of Linux it
actually will automatically

open with the package installer; and, I can install it that way OK.

It's finished installing, now, I can run it. And once you get Visual Studio Code
running or just "code" as we call

it or "vs code", (I guess has got lots of names there),

you might want to go into the Extensions and look for Docker. The one that's
just called Docker, install

that, and that will allow syntax highlighting and little extra features whenever
you're editing the Docker

files in this course. A a nice feature there, is if you're in a directory and
you just type code

with a dot after it, it'll actually open a visual studio code in that directory.

So it's sort of a shortcut to get all the files from my course up in your visual
studio code.

OK.

And the last little tip we're going to talk about real quick is customizing your
terminal. The nice

thing is on Linux is everything is pretty great

out of the box. You have a nice looking terminal usually that comes with Linux.

It works with all the features of Docker and one of the things you'll notice is
the command line completion.

That's tab completion that you may have used for a long time where if you're
typing a command in Linux

in your shell and you just hit the tab key it will auto finish that and actually
show you features around

the options for that command.

So if I just type docker and then hit tab twice it'll actually show me all the
different commands I

can use here.

So I could type Docker

image and then hit tab twice again it gives me another one.

And I could say ls, and then I get hit tab twice again and it would give me all
the options that I

would have for that particular command.

And that all works out-of-the-box after installing.

You don't have to do anything to get that feature. With Mac and Windows, you
have to go through extra steps

in you case you watch those videos.

But in case you're seeing stuff in my course, like the fact that I use the Zsh
shell, and then maybe I have

different colors that you like or features, you just need to check out

www.bretfisher.com/shell, and I list everything that I use in my custom shell in
a Mac that will

actually work pretty easily inside Linux. So I customize my vim, for example,
and other various things

of my shell.

So feel free to check that out.

But it's absolutely not required for this course.

I just get a lot of questions on it.

So I wanted to give you some more info before we get started.

OK so hopefully you have Docker working on your machine.

So let's just review the tips and tricks that we just talked about and all the
things we got installed.

After installing Docker, make sure you also get Compose and Machine and you can
get them from those

two links or from the GitHub page that I showed you. I didn't mention this
earlier but later in the

course, when we get to the sections on swarm, you'll be using Docker Machine to
create more VMs, whether

on your machine or in the cloud, that run Docker. So you can have multiple nodes
running Docker. Docker

Machine is just one of the ways that you can actually set up another machine to
run Docker. You can

check that out any time,

but you won't need it till near the end of the course.

And if you'll remember we talked about Visual Studio Code, so you can check that
out.

And bonus! If you're on Linux then bash completion for the commands just works
and you don't have to

worry about.
