FROM debian:jessie

MAINTAINER Zach Deibert <zachdeibert@gmail.com>

#based on dockerfile by Jo Shields <jo.shields@xamarin.com>
#based on dockerfile by Michael Friis <friism@gmail.com>

RUN apt-get update \
	&& apt-get install -y curl \
	&& rm -rf /var/lib/apt/lists/*

RUN apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 3FA7E0328081BFF6A14DA29AA6A19B38D3D831EF

RUN echo "deb http://download.mono-project.com/repo/debian wheezy/snapshots/3.10.0 main" > /etc/apt/sources.list.d/mono-xamarin.list \
    && echo "deb http://download.mono-project.com/repo/debian 310-security main" >> /etc/apt/sources.list.d/mono-xamarin.list \
    && echo "deb http://download.mono-project.com/repo/debian wheezy-libjpeg62-compat main" >> /etc/apt/sources.list.d/mono-xamarin.list \
	&& apt-get update \
	&& apt-get install -y mono-devel fsharp mono-vbnc nuget \
	&& rm -rf /var/lib/apt/lists/*

RUN mozroots --machine --import --sync --quiet

