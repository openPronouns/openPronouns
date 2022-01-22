# openPronouns

[![Join the chat at https://gitter.im/openPronouns/community](https://badges.gitter.im/openPronouns/community.svg)](https://gitter.im/openPronouns/community?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

openPronouns is a project to allow federated pronoun fetching.

## About
So, as stated above, the aim of the project is to produce a common API to allow for services to fetch pronouns for its users. Currently, most services provide their own systems to display pronouns, which is fine. However, there have been a couple of services (such as pronouny and pronouns.page) that provide a full profile for people to display their pronouns, honourifics, etc. This project takes the ideas of those services one step forward, enabling services to simply look up a profile by email or by username (in the format of @username:server.tld). The aim is to allow this lookup for both first and third party implementations.  

For example, a Discord bot could use openPronouns to look up an user ID on the main identity server to give users a role for the pronouns stored by the user's homeserver. Should Discord then decide to integrate with openPronouns, they could either search the user ID on the identity server, search through federation with an oP username, search through the federation system for a profile with their user's email address, or a hybrid of the three. 

## Projects
 Name | Description | Released?
 -----|-------------|----------
 [Odin](https://github.com/openPronouns/Odin) | Backend server written in JS/TS | ❎
 
## Structure
There are three main components to openPronouns, the "backend", the "identity server", and the "frontend".

### Identity Server
The reason for an identity server is to allow 3rd party integrations to work with openPronouns. If we use the Discord example from above, we will notice an issue. A Discord bot generally doesn’t have access to the email address, the two options would be for the bot to generate its own database or for it to access an identity server. However, there’s also a further issue with email. Unless, for example, Google was to set a DNS record pointing to a "backend" server for gmail.com, there would be no way to look someone up via email. Due to this limitation, it kind of means that we need an identity server to mitigate it.  

However, an end user would be able to set their identity server should they wish. This means that a Discord bot provider would be able to host their own "identity server" to host this information. This means that in theory the Discord bot would be able to create an identity server/backend hybrid to host information as a backup for those who don’t use the service (i.e. a user would be able to submit their pronoun to the bot without needing an account with any openPronoun compatible service).
