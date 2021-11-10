# should-pulp3-have-installer-packages
Why I fear pulp has no installer and does not even [want it](https://github.com/pulp/pulpproject.org/blob/a7a604d3a34536c4a83fea4f66704d747e2aa9ea/_posts/2021-03-22-pup-installer-overview.md#what-motivated-pulp-to-change-the-primary-installation-method).

### Summary
I don't consider https://github.com/pulp/pulp_installer an installer but "orchestrator".
e.g. When it says it supports fedora 35, that does not mean pulp is installed into fedora, but
it is supported to enslave a fedora 35 host to become an orchestrated pulp-system.
The result is, I don't have an installation, but an integration project.
In the rest of the file I have reiterated what an installer-package is for me to highlight,
where pulp_installer probably never can be an installer. For You to choose, if You like to clarify,
what not expect from it or what instead to develop to call it "pulp the installer , the all-current-supported thing."


*"the thing , that puts it in my system"* 

## Terms:
*I just listed here what makes up the term to spare a complete definition.* 
software system
* kubernetes
* docker in one
* ubuntu/debian
* fedora

software distribution
* pulpcore 
* severall redhat maintained plugins
* community plugins that satisfy all distribution-wide agreements

piece of software/componet
 * server or client plugin in its own repository/ies


# installer package definition:
supports the folling operations:
* install 
* upgrade 
* remove.

An installer package takes a piece of software or a distribution of software out of its
authorative archive(s) and hands the code to software systems install routine
according to the software systems conventions. 
It Provides and initial configration, which puts the piece of software or distrubtion in a installed/or running state,
which later can be verified by the software systems standard methods.
If integrations to other services in the software system are neccesary the installer package is either responsible
for interacting with these services in accordance with acceptable practices of the software system or if not possible
to provide the services itsself without conflicting with these services should they be installed  in the software system alongside standalone.

On upgrade:
The installer package respects the local administrators configuration and 
software systems conventions on upgrading integration configurations or operations to its installed services.


# What it needs:
An installer package has requiements:
* needs to have access to the authorative archive of 
  * the piece of software 
  * or the components + the components versions that comprise the distribution.
  * a distribution-wide agreement on what versions of what component make up the distribution is necesary.
* it needs knowledge about the software system.
* needs to ensure that the code adheres to the software systems requirements (to satisfy "installed/running" ).
  * if analysis shows that this is not given it needs to know the dependencies to be able to "build" (even if building just choosing what liberies to use and what libraries to bundle)
* it needs knowledge about services the distruibution depends on (runtime dependency)
 * a distribution-wide agreement with all devs on one valid to service-integration-configuration thus is mandatory.  
* it needs to know what constitudes a succefull start
* it needs to know the mandantory configuration values
  * a distribution-wide agreement with all devs is neccesary to establish what configuration values are neccesary to stand up the service.
  * an installer usually has the right to refuse to be concerned with other configuration values than mandatory or integration.
* the distribution wide agreements are only coordinated by the installer team but owned and expressed by all participating projects.
  
# What status does an installer package have in a project:
* it is release critical to the distribution.
* the translation of "an installer is outdated" is:
  * since the integration tests (can be as little as insralled ok/running) to Your prefered software-system fail, we don't "natetively" support Your software system in the "pulp3-distribution" You chose.
  


