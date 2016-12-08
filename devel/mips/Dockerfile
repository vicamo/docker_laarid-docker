# DO NOT EDIT!!! GENERATED FROM Dockerfile.template.
FROM vicamo/buildpack-deps:stretch-mips

ENV LAARID_USER=laarid
ENV LAARID_HOME=/home/${LAARID_USER}

RUN apt-get update -qq \
	&& apt-get install --no-install-recommends -y \
		apt-transport-https \
		autoconf-archive \
		autopoint \
		build-essential \
		ccache \
		devscripts \
		dh-autoreconf \
		dirmngr \
		equivs \
		gnupg \
		libfile-fcntllock-perl \
		lintian \
		sudo \
	&& apt-get clean \
	&& rm -f /var/lib/apt/lists/*_dists_*

# Don't install any packages from bintray now. Error: "Insufficient
# information available to perform this download securely".
#
# RUN (echo "deb https://dl.bintray.com/laarid/main stretch main" | tee /etc/apt/sources.list.d/bintray.list) \
# 	&& apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 379CE192D401AB61 \
# 	&& apt-get update -qq \
# 	&& apt-get install --no-install-recommends -y --allow-unauthenticated
# 		libbionic0-dev \
# 	&& apt-get clean \
# 	&& rm -f /var/lib/apt/lists/*_dists_*

RUN useradd --comment 'LAARiD Development Account' \
		--home ${LAARID_HOME} --create-home \
		--shell /bin/bash \
		${LAARID_USER} \
	&& (echo "${LAARID_USER}:laarid" | chpasswd) \
	&& adduser ${LAARID_USER} sudo \
	&& (echo "${LAARID_USER} ALL=NOPASSWD: ALL" > /etc/sudoers.d/laarid) \
	&& chmod 0440 /etc/sudoers.d/laarid

VOLUME ["${LAARID_HOME}"]
WORKDIR ${LAARID_HOME}
USER ${LAARID_USER}
