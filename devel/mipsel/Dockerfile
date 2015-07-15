FROM vicamo/buildpack-deps:stretch-mipsel

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
	&& (echo "deb https://dl.bintray.com/laarid/main stretch main" | tee /etc/apt/sources.list.d/bintray.list) \
	&& apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 379CE192D401AB61 \
	&& apt-get update \
	&& apt-get install --no-install-recommends -y --force-yes \
		libbionic0-dev \
	&& apt-get clean \
	&& rm -f /var/lib/apt/lists/*_dists_*
