OK let's do some fun stuff. In this lecture,

we're going to quickly talk about the difference between images and containers.
Then we're going

to jump right into playing around with a container. We're going to start it,

we're going to stop and remove it, and do some common administrative functions.
Then we're going to

check out the container logs and the processes running in our container.

So before we jump in real quick, it's good to know the difference between an
image and a container. An

image is the binaries and libraries and source code that all make up your
application. The container

is a running instance of that image.

Now, you can have many containers all based off the same image. In this lecture,

we're going to be using the Open Source Nginx web server. So we'll be starting
our containers

based off that Nginx image. We get all of our images from registries. Registries
are kind of like

what GitHub is to source code. Image registries are for container images and the
default one for Docker

is Docker Hub, which you can check out at

hub.docker.com.

We'll play more with that later.

But for now be aware that these two things are quite different, and in the next
section we're going to

jump in to images.

But for now let's focus on containers.

OK now we're going to start a new container and use some Docker commands to
manage that container.

docker container run --publish 80:80 nginx.

Don't worry if you don't know what all that means. We'll go through it all in a
minute.

I'll hit enter...

switch over to my browser, and type in localhost.

There we go.

Our Nginx server is listening. I can hit refresh several times and you'll see
the log entries

happening in our command line here.

Now what did we just do? In the background,

the Docker engine actually looked for an image called nginx, and it pulled down
the latest image for

nginx from Docker Hub. Then it started it as a new process in a new container
for us to use.

The published part of the command exposes my local port 80 on my local machine
and sends all traffic

from it to the executable running inside that container on port 80.

And since Nginx is a web server it's going to default to port 80 and the traffic
just forwards automatically

through my browser to my local host and into that container.

But we don't always want this thing running in the foreground inside of our
command line.

So let's hit Control c and I'm going to hit the Up Arrow and I'm going to back
up a little bit and type in

detach.

Now detach tells Docker to run it in the background.

And we get back the unique container ID of our container.

And every time you run a new container you get a new unique ID.

So if we go back over to our browser and hit refresh a couple of times you can
see that it's still running.

So let's do a command to list our containers: docker container ls

And you'll see the one that's still running here.

It's matching the container ID of the command we just ran. You'll see the
container still running

that we just started.

So let's stop that container real quick: docker container stop. 

Then the container ID. For the container ID I only have to type the first

few digits, enough for it to be unique, and I stopped it.

Now if I do a docker container ls, you'll notice nothing shows up.

So the ls command only shows by default running containers.

If I do an ls -a, I get back two. Now, why do I get two?

When we ran each time the docker container run command, it started a new
container from that Nginx

image. You'll notice on the right here that there's these random names. We
didn't use these.

How did we get these?

So the container ID is always created for us.

And the name is also required to be unique.

And if we don't specify it, it will be created for us. We can always name
something ourselves,

but if we let it pick its own, it's actually an interesting little bit of
history around Docker is that

they've had this for years now that that name will randomly be generated from an
open source list

of adjectives and the surnames of notable hackers or scientists.

And it's pretty funny sometimes you'll get some really peculiar names in there.

So let's create a new one. docker container run. Put in our publish

and our detach.

But this time we're going to specify a name. I'm going to call it webhost nginx.

And now if I do my docker container ls -a you'll see three containers.

The one we just started. It has a name of webhost and then the two that we
previously started and

then stopped.

Since we're not running this in the foreground anymore, we can't see the logs.

So let's go back to our browser and I'm going to hit refresh a couple of times
to generate some logs.

Then back to our terminal and I'll do docker container logs webhost. And it will
spit out the latest

logs in the webhost.

There's a couple of options you want to play around with on the logs command to
have it follow the

logs automatically or it can just capture the last few log events so that you
don't end up with the

entire log file being dumped to your screen.

We can also use some other docker container commands to check on that running
container. We can

try docker container top. You can see the help there.

That lets us know we need to specify container name webhost. You can see this is
the process running

inside the container.

Now for Nginx we don't need to necessarily know all this but it's just
interesting to note that with

Nginx,

there's actually a master process and then it spawns worker processes based on
the configuration.

Again we can always type docker container and --help to get a list of all the
commands we

could try on that container.

Now let's clean up what we just did.

So let's do a docker container.

ls -a, and that's going to list all three of my containers.

Now, I'm actually going to remove all three at the same time.

Sometimes subcommands of Docker can actually take multiple values.

So in this case I can do a docker container rm and then I can actually specify
63f 690 and ode.

whoops 0de.

So I got an error. What just happened here?

All right. The first two were safely deleted.

The third one it's telling me I can't remove a running container because it's a
safety measure.

It makes sure that you don't accidentally remove the actual process that's still
running. If you do

a docker container ls you'll see we still have one running.

Now I could actually do a docker container stop to stop it first and then remove
it.

But I'm actually going to do a docker container rm -f for force and 63f. And
there we go.

Now if I do a docker container ls -a you'll see that nothing's there.

So now we've cleaned up our mess.

OK.

So in just a matter of minutes we were able to use a single command to download
and run an Nginx

web server with a default configuration listening on port 80 and then we were
able to create several

of those, play with the logs and then remove the containers to clean up what we
had done.

Search all course questions
