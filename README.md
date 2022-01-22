# openPronouns

[![Join the chat at https://gitter.im/openPronouns/community](https://badges.gitter.im/openPronouns/community.svg)](https://gitter.im/openPronouns/community?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

openPronouns is a project to allow federated pronoun fetching.

## About
So, as stated above, the aim of the project is to produce a common API to allow for services to fetch pronouns for its users. Currently, most services provide their own systems to display pronouns, which is fine. However, there have been a couple of services (such as pronouny and pronouns.page) that provide a full profile for people to display their pronouns, honourifics, etc. This project takes the ideas of those services one step forward, enabling services to simply look up a profile by email or by username (in the format of @username:server.tld). The aim is to allow this lookup for both first and third party implementations.  

For example, a Discord bot could use openPronouns to look up an user ID on the main identity server to give users a role for the pronouns stored by the user's homeserver. Should Discord then decide to integrate with openPronouns, they could either search the user ID on the identity server, search through federation with an oP username, search through the federation system for a profile with their user's email address, or a hybrid of the three. 
