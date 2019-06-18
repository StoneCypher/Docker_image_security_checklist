# docker_image_security_checklist
Let's centralize what needs to be done for any arbitrary docker image's security

This list can then just be copy-pasta-ed into a given readme to validate the work later

## Checklist

1. [ ] Blind the docker images to anything on the network except things they need to be able to see
1. [ ] Reduce the privileges of the `docker` user
    * TODO: Specific list pending
1. [ ] Non-public connections between microservices are all authenticated
1. [ ] Consider a `metadata reverse proxy`
    * TODO: Explanation is warranted here
1. [ ] Remember to use load balancers in the fashion of firewalls
1. [ ] (not enough notes were taken) Reverse DNS
1. [ ] Be careful to extensively lock your database down
1. [ ] Set up periodic monitoring of time-limited resources like SSL certificates
1. [ ] Uptime monitors
1. [ ] Resource usage monitors
1. [ ] Catastrophic takeover replacement plan
1. [ ] Hard-specify your operating system version

## AWS specific stuff
1. [ ] Where possible, use AWS VPC
1. [ ] In Cloudtrail, set up another account unrelated to the production account
    1. [ ] Logs go there, to raise the workload for an attacker hiding their tracks
    1. [ ] Use a role that cannot edit logs after the fact
    1. [ ] Use completely distinct authentication
1. [ ] Look into SSM as an alternative to SSH, and in that case, disable SSH
