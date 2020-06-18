# Braden's Ansible Roles

These are ansible roles that allow one to easily deploy containerized applications (with automatic HTTPS and access to PostgreSQL and Redis). The idea is that you only need a commodity $5/mo VM from a provider like DigitalOcean to run your app, with the ease of use that more expensive systems have. If you need to scale your app at some point, you can re-use the database VM provisioned here and just move the application containers themselves out into a Kubernetes cluster behind a proper load blaancer.

To use, provision one or two **Ubuntu 20.04 LTS** VMs from your favorite provider. You can put everything on a single VM, or optionally use two VMs: one for the database servers (PostgreSQL + Redis), and another for the docker containers. Inter-VM communication will be encrypted via spiped.

The data in PostgreSQL will get backed up daily by a cron job, but you'll need to use your own process to regularly download it via SSH or  upload it elsewhere (e.g. S3).
