# Codesafe
Codesafe is a computer science (CS) education platform focused on teaching concepts and skills relevant to software engineering (SE) and software security, with the goal of also driving upskilling and reskilling for individuals looking to break into the tech industry or learn how to develop software and scripts for their respective professions. The concepts behind Codesafe originated from our proposal under the same name to the [2023-24 DARPA’s Building an Adaptive and Competitive Workforce Track of the Tools Competition](https://tools-competition.org/23-24-darpa-winners/), which is organized through [The Learning Agency](https://the-learning-agency.com/) and a program of [Renaissance Philanthropy](https://www.renaissancephilanthropy.org/). 

Some other concepts we explore include challenge-based and scenario-based learning, AI and LLM usage within CS and SE education (on the student and instructor side), code comprehension in the era of LLMs, and teaching real-world software security, safety, and reliability. You can view a glossary for Codesafe research-specific terminology that we have developed to ensure that the research team and research participants have an aligned understanding [here](https://docs.google.com/document/d/1Hcm1xn5QpwtGQimfLPoqyAXZqVzwGtAiL-LwtYEkXp8/edit?tab=t.0).

The platform is heavily inspired by [pwn.college](https://pwn.college/), created by faculty and grad students at Arizona State University’s [SEFCOM Lab](https://sefcom.asu.edu/). Codesafe’s behind-the-scenes infrastructure is a fork of their DOJO infrastructure, which in turn is heavily inspired by "capture-the-flag" (CTF) challenges in the field of cybersecurity. We aim to apply the CTF concept to create challenges that are grounded in the software engineering experience, creating a scenario-driven, gamified learning experience that can be delivered at scale.

### Current Set-Up
If you are attempting to deploy Codesafe yourself directly from this repo, there are some hard-coded values in the code that are customized for my test deployment of Codesafe on a DigitalOcean droplet + configured to also have a named domain with HTTPS. Here are where the values are hard-coded:
- SSH port 22 for the main Docker container is set to be 4040, see [this commit](https://github.com/StengoS/codesafe/commit/09fb7e307db90ef162c8ab14a37842bc7e3ece68).
- HTTPS configuration, see [dojo/dojo-init](./dojo/dojo-init).


### Shout-Outs to ASU's pwn.college
Codesafe is currently powered by pwn.college's DOJO infrastructure, which you can best experience at [pwn.college](https://pwn.college). 
All credit for the DOJO infrastructure and the conceptualization behind it goes to all those listed in the 
"Greetz" section of the website and to all those listed as contributors on their repos. pwn.college is maintained 
by a team of faculty and students at Arizona State University and used primarily in their cybersecurity courses. 
All of their course materials and corresponding challenges are available on [pwn.college](https://pwn.college), so go check it out for hands-on cybersecurity and hacking!

For more information on the DOJO infrastructure, please check out our [Documentation](./docs):
- [📜 History](./docs/history.md)
- [🏛️ Architecture](./docs/architecture.md)
- [🚀 Deployment](./docs/deployment.md)
- [🚩 Challenge](./docs/challenge.md)
- [💻 Development](./docs/development.md)
(Copied over from pwn.college's DOJO repo.)

### Contact
For any questions or feedback, you can reach out to:
- Steven Ngo, `skngo1@uci.edu`
