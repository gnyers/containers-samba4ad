FROM ubuntu:20.04


ENV DEBIAN_FRONTEND=noninteractive
RUN apt update
RUN \
	apt-get install -y samba krb5-user krb5-config winbind smbclient \
			libpam-winbind libnss-winbind samba busybox; \
	busybox --install; \
	mv /etc/samba/smb.conf /etc/samba/smb.conf.bak; \
	mv /etc/krb5.conf /etc/krb5.conf.bak;

ENV \
    S4AD_FQDN='' \
    S4AD_IPV4='' \
    S4AD_WORKGROUP='' \
    S4AD_REALM='' \
    S4AD_ADMINPW='' \
    S4AD_MACHINEPW='' \
    S4AD_KRBTGTPW='' 


COPY /etc/  /etc

# Use the built-in init prg of busybox
CMD /sbin/init


