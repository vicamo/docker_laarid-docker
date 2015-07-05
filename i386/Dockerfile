FROM vicamo/buildpack-deps:stretch-i386

RUN apt-get update \
	&& apt-get install --no-install-recommends -y --force-yes \
		autopoint \
		devscripts \
		dh-autoreconf \
		equivs \
		lintian \
	&& apt-get clean \
	&& rm -f /var/lib/apt/lists/*_dists_*
