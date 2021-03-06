---
layout: post
title:  Getting Around in Vienna (with the Kind Assistance of Geospatial Open Source Software)
date:   2014-03-21
author: Stephan Krause
tags:   status
icon:   fa-info-circle
---

Hi sprinters, ITS Vienna Region is a silver sponsor of the OSGeo Code Sprint 2014. In many
ways, geospatial open source software has helped us providing our services, so
the Code Sprint is a great occasion to give a little bit back to you.

Who we are and what we are doing
--------------------------------

[ITS Vienna Region](http://www.anachb.at/mehr) is a division of
Verkehrsverbund Ost-Region \([VOR](http://www.vor.at)\). VOR coordinates the
public transport in and around Vienna.

ITS Vienna Region provides intermodal traffic information for the northeastern
part of Austria on its web site
[anachb.at](http://www.anachb.at/?set_language=en&cl=en). There's an AnachB app
for Androids and iPhones, too.

We operate and contribute to the so called Graph Integration Platform
\([GIP](http://www.gip.gv.at/home-en.html)\), a comprehensive intermodal graph
of the Austrian transport networks including roads, rails, subways, tramways,
ferries, hiking trails and biking tracks and everything else.

What we can do for you
----------------------

You can use our services to
[find the best way](http://www.anachb.at/?set_language=en&cl=en) to get around
in Vienna and its surroundings walking, using public transport, bikes or cars.
Our goal is to provide up-to-date information about all traffic modes and
thereby encourage people to use the more environmentally friendly ones.

What you do for us
------------------

For our services and in our background processes, we use lots of free and open
source GIS software (and lots of commercial software as well, I have to admit).

The levels of service calculated by our traffic state simulations, for instance,
are provided to the
[City of Vienna interactive map](http://www.wien.gv.at/stadtplan/en/)
\(operated by MA14, your venue sponsor\) and to the public as a WMS layer using
*MapServer*.

Our upgraded, new user interface will be based on *OpenLayers*. A 
[public beta](http://beta.verkehrsauskunft.at/bin/query.exe/en?) with a
slightly different design is operated by Verkehrsauskunft &Ouml;sterreich
\([VAO](http://www.verkehrsauskunft.at/)\), the upcoming integrated platform for
intermodal traffic information in Austria.

In the backend, we use *PostGIS* for hosting a copy of our network graph and
referencing traffic messages and detector locations onto the links. Accurately
locating data on the network is essential for providing up-to-date information
about traffic volumes, congestions, accidents and other disturbances on the
roads.

One of our most popular services is the bike routing interface. It uses data
about slope angles for calculating the routes and provides height profiles for
the results. The underlying data have been generated by referencing DEM data
onto the network graph using the Python bindings of *GDAL/OGR*.

There's a lot more to tell, probably too much for a blog post :-) . So, finally:

*Thanks to you and all those who contribute to free and open source geospatial
software and a happy code sprint to everybody!*
