---
title: OVirt 3.6.4 Release Notes
category: documentation
authors: didi, sandrobonazzola, rafaelmartins
---

# oVirt 3.6.4 Release Notes

The oVirt Project is pleased to announce the availability of oVirt 3.6.4 first release candidate as of March 15th, 2016.

oVirt is an open source alternative to VMware vSphere, and provides an awesome KVM management interface for multi-node virtualization. This release is available now for Red Hat Enterprise Linux 6.7, CentOS Linux 6.7 (or similar) and Red Hat Enterprise Linux 7.2, CentOS Linux 7.2 (or similar).

To find out more about features which were added in previous oVirt releases,
check out the [previous versions release notes](http://www.ovirt.org/develop/release-management/releases/).
For a general overview of oVirt, read [the Quick Start Guide](Quick_Start_Guide)
and the [about oVirt](about oVirt) page.

## Install / Upgrade from previous versions

### Fedora / CentOS / RHEL

## CANDIDATE RELEASE

In order to install oVirt 3.6.3 Release Candidate you've to enable oVirt 3.6 release candidate repository.

In order to install it on a clean system, you need to install

`# yum localinstall `[`http://resources.ovirt.org/pub/yum-repo/ovirt-release36.rpm`](http://resources.ovirt.org/pub/yum-repo/ovirt-release36.rpm)

And then manually add the release candidate repository for your distribution to **/etc/yum.repos.d/ovirt-3.6.repo**

**For CentOS / RHEL:**

      [ovirt-3.6-pre]
      name=Latest oVirt 3.6 pre release
      baseurl=http://resources.ovirt.org/pub/ovirt-3.6-pre/rpm/el$releasever
      enabled=1
      skip_if_unavailable=1
      gpgcheck=1
      gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-ovirt-3.6

**For Fedora:**

      [ovirt-3.6-pre]
      name=Latest oVirt 3.6 pre release
      baseurl=http://resources.ovirt.org/pub/ovirt-3.6-pre/rpm/fc$releasever`
      enabled=1
      skip_if_unavailable=1
      gpgcheck=1
      gpgkey=file:///etc/pki/rpm-gpg/RPM-GPG-ovirt-3.6

If you are upgrading from a previous version, you may have the ovirt-release35 package already installed on your system. You can then install ovirt-release36.rpm as in a clean install side-by-side.

Once ovirt-release36 package is installed, you will have the ovirt-3.6-stable repository and any other repository needed for satisfying dependencies enabled by default.

If you're installing oVirt 3.6.4 on a clean host, you should read our
[Quick Start Guide](Quick Start Guide).

If you are upgrading from oVirt < 3.5.0, you must first upgrade to oVirt 3.5.0 or later. Please see [oVirt 3.5.6 Release Notes](oVirt 3.5.6 Release Notes) for upgrade instructions.

For upgrading now you just need to execute:

      # yum update "ovirt-engine-setup*"
      # engine-setup

### oVirt Hosted Engine

If you're going to install oVirt as Hosted Engine on a clean system please follow [Hosted_Engine_Howto#Fresh_Install](Hosted_Engine_Howto#Fresh_Install) guide.

If you're upgrading an existing Hosted Engine setup, please follow [Hosted_Engine_Howto#Upgrade_Hosted_Engine](Hosted_Engine_Howto#Upgrade_Hosted_Engine) guide.

### oVirt Live

A new oVirt Live ISO is available at:

[`http://resources.ovirt.org/pub/ovirt-3.6-pre/iso/ovirt-live/`](http://resources.ovirt.org/pub/ovirt-3.6-pre/iso/ovirt-live/)

## Bugs fixed

### oVirt Engine

 - [BZ 1310390](https://bugzilla.redhat.com/1310390) - Restore snapshot with only subset of vm's disks will stuck the vm in image locked state
 - [BZ 1311616](https://bugzilla.redhat.com/1311616) - The API crashes when parsing unexpected version numbers

### VDSM

 - [BZ 1303410](https://bugzilla.redhat.com/1303410) - [ipv6] vdsm-network reconvigures network due to unsolicited ipvp6 address
 - [BZ 1308839](https://bugzilla.redhat.com/1308839) - [vmfex-hook] - Failed to run VM with vdsm-hook-vmfex-dev-4.17.20

### oVirt Hosted Engine Setup

 - [BZ 1306825](https://bugzilla.redhat.com/1306825) - hosted-engine upgrade fails after upgrade hosts from el6 to el7
 - [BZ 1311317](https://bugzilla.redhat.com/1311317) - Unattended Ovirt host deploy fails on second host when the engine already imported the hosted-engine storage domain

### oVirt Hosted Engine HA

 - [BZ 1316143](https://bugzilla.redhat.com/1316143) - 3.6 hosted-engine hosts can't be added properly to 3.6 host cluster that was started with 3.4.

