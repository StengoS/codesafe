# Codesafe
[Codesafe description to be added.]

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
