FROM vicamo/buildpack-deps:stretch-ppc64el

ENV LAARID_USER=laarid
ENV LAARID_HOME=/home/${LAARID_USER}

RUN apt-get update \
	&& apt-get install --no-install-recommends -y --force-yes \
		apt-transport-https \
		autoconf-archive \
		autopoint \
		ccache \
		devscripts \
		dh-autoreconf \
		equivs \
		libfile-fcntllock-perl \
		lintian \
		sudo \
	&& (echo "deb https://dl.bintray.com/laarid/main stretch main" | tee /etc/apt/sources.list.d/bintray.list) \
	&& apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 379CE192D401AB61 \
	&& apt-get update \
	&& apt-get install --no-install-recommends -y --force-yes \
		libbionic0-dev \
	&& apt-get clean \
	&& rm -f /var/lib/apt/lists/*_dists_*

RUN useradd --comment 'LAARiD Development Account' \
		--home ${LAARID_HOME} --create-home \
		--shell /bin/bash \
		${LAARID_USER} \
	&& (echo "${LAARID_USER}:laarid" | chpasswd) \
	&& adduser ${LAARID_USER} sudo

VOLUME ["${LAARID_HOME}"]
WORKDIR ${LAARID_HOME}
USER ${LAARID_USER}
