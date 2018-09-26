# testapps
## Test applications for Ops CI/CD pipe 
This repo contains the code for deploying all the test applications that are assembled to vet my infrastructure in my lab. Eventually it will also house the tests that will do the actual measurement. 

I am using ansible to drive Satellite. The cvpublisher project contains the roles and plays that orchestrate the overall activity. This repo contains some basic examples that originated in the ansible-examples repo. I am modifying them somewhat to my needs, however, they can still serve as useful examples. Currently, I am updating the syntax and style for current (ansible 2.6.1 / Tower 3.3.0) releases.

These roles can stand on their own, but to see how I integrate them see the cvpublisher project.

Have fun!
