FROM ubuntu

EXPOSE 3000 90
RUN apt-get update -yq && apt-get install -yq --no-install-recommends \
		postfix
RUN apt-get install -yq \
			build-essential \
			curl \
			ca-certificates \
			openssh-server
WORKDIR /

RUN curl -s https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh | bash
CMD ["bash", "script.deb.sh"]
RUN apt-get install -yq gitlab-ce
RUN apt-get update -yq && \
# echo "Europe/Dublin" > /etc/timezone && \
# dpkg-reconfigure -f noninteractive tzdata && \
			export DEBIAN_FRONTEND=noninteractive DEBCONF_NONINTERACTIVE_SEEN=true && \
			apt-get install -yq tzdata && \
			apt-get clean && rm -rf /tmp/* /var/tmp/* /var/lib/apt/lists/*

  RUN touch /entrypoint.sh && \
										   chmod 755 entrypoint.sh && \
										   echo "/opt/gitlab/embedded/bin/runsvdir-start&\nexport EXTERNAL_URL ="localhost"\ngitlab-ctl reconfigure\ngitlab-ctl start\ntail -f /dev/null" > entrypoint.sh

RUN bash entrypoint.sh


# https://www.linode.com/docs/development/version-control/install-gitlab-with-docker/
