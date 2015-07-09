FROM vicamo/buildpack-deps:stretch-armel

RUN apt-get update \
	&& apt-get install --no-install-recommends -y --force-yes \
		apt-transport-https \
		autopoint \
		ccache \
		devscripts \
		dh-autoreconf \
		equivs \
		libfile-fcntllock-perl \
		lintian \
	&& apt-get clean \
	&& rm -f /var/lib/apt/lists/*_dists_*

# There is no packages available for armel yet.
# See https://github.com/laarid/bionic/issues/10
#
#	&& (echo "deb https://dl.bintray.com/laarid/main stretch main" | tee /etc/apt/sources.list.d/bintray.list) \
#	&& apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 379CE192D401AB61 \
#	&& apt-get update \
#	&& apt-get install --no-install-recommends -y --force-yes \
#		libbionic0-dev \
