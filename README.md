# Codesafe
Codesafe is a computer science (CS) education platform focused on teaching concepts and skills relevant to software engineering (SE) and software security, with the goal of also driving upskilling and reskilling for individuals looking to break into the tech industry or learn how to develop software and scripts for their respective professions. The concepts behind Codesafe originated from our proposal under the same name to the [2023-24 DARPA’s Building an Adaptive and Competitive Workforce Track of the Tools Competition](https://tools-competition.org/23-24-darpa-winners/), which is organized through [The Learning Agency](https://the-learning-agency.com/) and a program of [Renaissance Philanthropy](https://www.renaissancephilanthropy.org/). 

Some other concepts we explore include challenge-based and scenario-based learning, AI and LLM usage within CS and SE education (on the student and instructor side), code comprehension in the era of LLMs, and teaching real-world software security, safety, and reliability. You can view a glossary for Codesafe research-specific terminology that we have developed to ensure that the research team and research participants have an aligned understanding [here](https://docs.google.com/document/d/1Hcm1xn5QpwtGQimfLPoqyAXZqVzwGtAiL-LwtYEkXp8/edit?tab=t.0).

The platform is heavily inspired by [pwn.college](https://pwn.college/), created by faculty and grad students at Arizona State University’s [SEFCOM Lab](https://sefcom.asu.edu/). Codesafe’s behind-the-scenes infrastructure is a fork of their DOJO infrastructure, which in turn is heavily inspired by "capture-the-flag" (CTF) challenges in the field of cybersecurity. We aim to apply the CTF concept to create challenges that are grounded in the software engineering experience, creating a scenario-driven, gamified learning experience that can be delivered at scale.

## Deployment Steps
### Prerequisites
Install [Docker](https://www.docker.com/get-started/). Docker greatly simplifies the deployment of Codesafe into only a few commands. If you need additional help, follow the steps based on your operating system:
* Windows - https://docs.docker.com/desktop/setup/install/windows-install/ 
  * If you are on Windows, it’s highly recommended that you also have Windows Subsystem for Linux (WSL). For further instructions, see: https://learn.microsoft.com/en-us/windows/wsl/install. 
  * You will need Docker Desktop running while working in WSL.
* Mac - https://docs.docker.com/desktop/setup/install/mac-install/ 
* Linux - https://docs.docker.com/desktop/setup/install/linux/

Verify that you have successfully installed Docker with:
```
$ docker -v
```

### Setting Up Codesafe
Run the commands below:

```
$ git clone https://github.com/StengoS/codesafe.git
$ cd codesafe/
$ docker build -t pwncollege/dojo "."
$ modprobe br_netfilter
$ docker run --name dojo --privileged -v ".:/opt/pwn.college" -v "./data:/data" -p 4040:4040 -p 80:80 -p 443:443 -d pwncollege/dojo
```

***Note**: The usages of pwn.college around the repo and website are remaining artifacts, also considering that we are building Codesafe by extending pwn.college’s behind-the-scenes DOJO infrastructure. We will, at some point, adjust the naming scheme when appropriate.*

You will most likely need to wait for the Docker build and run commands to finish, which may take a few minutes. After running the last command, you can check its progress with the command below:

```
$ docker exec dojo dojo logs
```

Once the build is complete, you can access Codesafe locally at localhost.pwn.college. 

***Note**: Because the infrastructure uses a self-signed certificate, if you are on Firefox, the browser may not allow you to access the site (without even an option to ignore the warning). You may need to use an alternative browser, e.g., Chrome, to access the site.* 


### Current Set-Up
If you are attempting to deploy Codesafe yourself directly from this repo, there are some hard-coded values in the code that are customized for my test deployment of Codesafe on a DigitalOcean droplet + configured to also have a named domain with HTTPS. Here are where the values are hard-coded:
- SSH port 22 for the main Docker container is set to be 4040, see [this commit](https://github.com/StengoS/codesafe/commit/09fb7e307db90ef162c8ab14a37842bc7e3ece68).
- HTTPS configuration, see [dojo/dojo-init](./dojo/dojo-init).

<br> 


## Shout-Outs to ASU's pwn.college
Codesafe is currently powered by pwn.college's DOJO infrastructure, which you can best experience at [pwn.college](https://pwn.college). All credit for the DOJO infrastructure and the conceptualization behind it goes to all those listed in the "Greetz" section of the website and to all those listed as contributors on their repos. pwn.college is maintained by a team of faculty and students at Arizona State University and used primarily in their cybersecurity courses. All of their course materials and corresponding challenges are available on [pwn.college](https://pwn.college), so go check it out for hands-on cybersecurity and hacking!

For more information on the DOJO infrastructure, please check out [Documentation](./docs):
- [📜 History](./docs/history.md)
- [🏛️ Architecture](./docs/architecture.md)
- [🚀 Deployment](./docs/deployment.md)
- [🚩 Challenge](./docs/challenge.md)
- [💻 Development](./docs/development.md)
(These are copied over from pwn.college's DOJO repo.)

### Contact
For any questions or feedback, you can reach out to:
- Steven Ngo, `skngo1@uci.edu`
