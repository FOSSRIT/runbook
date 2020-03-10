IRC (Freenode)
==============

This page documents the [Internet Relay Chat](https://en.wikipedia.org/wiki/Internet_Relay_Chat "Internet Relay Chat - Wikipedia") (IRC) infrastructure for the FOSS@RIT community.
Currently, this only includes our presence on the [Freenode](https://freenode.net/ "official Freenode website") IRC network.


## Project registration

TODO…


## Cloaks

Cloaks are a type of "host mask" that replaces your IP address in IRC clients with a custom string of text.
The IRC protocol exposes your IP address or hostname by default when you join a channel.
When you authenticate with IRC's NickServ, a cloak replaces your IP address/hostname with the custom string.

Note that Freenode does not support the underscores (`_`) in cloaks.
Other non-alphanumeric characters may also not be supported and will be omitted from the cloak.

### Request a cloak

In order to receive a cloak, you must have completed the following steps:

1. Register your nick with NickServ
2. Set an email address with NickServ
3. Created an alternate nick and linked it to primary nick with NickServ

If you have not completed these steps, Freenode will not allow us to create your cloak.
For help doing these things, check out the [Nickname Registration help page](https://freenode.net/kb/answer/registration "Nickname Registration - freenode") on Freenode's website.

Once you have completed the above steps, you can request a new cloak.
Request a cloak by [opening a new issue](https://github.com/FOSSRIT/tasks/issues/new) on the [FOSSRIT/tasks](https://github.com/FOSSRIT/tasks) repository.

### Available cloaks

Members of the RIT community may choose from the following cloaks:

#### General

* `@rit/student/<your IRC nick>`
* `@rit/professor/<your IRC nick>`
* `@rit/faculty/<your IRC nick>`
* `@rit/alumnus/<your IRC nick>`
* `@rit/alumna/<your IRC nick>`
* `@rit/alum/<your IRC nick>`

#### RIT FOSS

Cloaks for the [RIT FOSS community](https://fossrit.github.io/about/).

* `@rit/foss/student/<your IRC nick>`
* `@rit/foss/faculty/<your IRC nick>`
* `@rit/foss/alumnus/<your IRC nick>`
* `@rit/foss/alumna/<your IRC nick>`
* `@rit/foss/alum/<your IRC nick>`

#### RITlug

Cloaks for the [RIT Linux Users Group](https://ritlug.com/about/).

* `@rit/ritlug/member/<your IRC nick>`
* `@rit/ritlug/alumnus/<your IRC nick>`
* `@rit/ritlug/alumna/<your IRC nick>`
* `@rit/ritlug/alum/<your IRC nick>`

### Granted cloaks

The table below is a list of community members who were issued IRC cloaks.

<!--
Please be mindful for accounts with the character "|".
You should look at the source because the formatted page does not show "|".
-->

| Real name        | NickServ account | RIT computer account | Cloak                            |
| ---------------- | ---------------- | -------------------- | -------------------------------- |
| Justin W. Flory  | jflory7          | jwf9260              | @rit/foss/captain/fedora.jflory7 |
| Chris Bitler     | VoidWhisperer    | crb2547              | @rit/foss/student/voidwhisperer  |
| Adam Hayes       | moondoggy        | abhsps               | @rit/alum/moondoggy              |
| Jennifer Herting | qwertos          |                      | @rit/alumna/qwertos              |
| Mike Nolan       | Nolski           | mpn3712              | @rit/foss/alumnus/nolski         |
| Nate Levesque    | thenaterhood     | ngl3477              | @rit/alum/thenaterhood           |
| Aidan Kahrs      | axk4545          | axk4545              | @rit/ritlug/member/axk4545       |
| Matt Soucy       | msoucy           | mas5997              | @rit/foss/alumnus/msoucy         |
| Wilfried Hounyo  | wilfriedE        | weh7221              | @rit/student/wilfriede           |
| Brendan McGeever | sacratoy         | btm4810              | @rit/foss/student/sacratoy       |
| Kevin M. Granger | KevinMGranger    | kmg2728              | @rit/foss/alum/kevinmgranger     |
| Christian Martin | ctmartin         | ctm2142              | @rit/foss/student/ctmartin       |
