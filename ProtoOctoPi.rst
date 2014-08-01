Fablab ProtoSpace Octoprint/OctoPi voor meerdere printers
=========================================================

In de `Github van Fablab-Protospace <http://github.com/Fablab-ProtoSpace>`_ leeft een fork van `OctoPi <https://github.com/guysoft/OctoPi>`_.

Installeren
-----------

OctoPi is een set scripts en fs aanpassingen op een vanilla raspbian distributie. Met OctoPi is het mogelijk om een fs image te maken die op de SD-kaart geplaatst wordt. Hier wordt enkel beschreven hoe op een al geinstalleerde Raspberry met Raspbian de ProtoSpace versie van Octoprint/OctoPi te installeren.

De actieve branch is voor de ProtoSpace OctoPi ontwikkeling is `devel-jeroen <https://github.com/Fablab-ProtoSpace/OctoPi/tree/devel-jeroen>`_.

Requirements
~~~~~~~~~~~~

#. Root privileges
#. Bash

Installatie
~~~~~~~~~~~

Op de raspberry voer de volgende commando's uit::

    git clone https://github.com/Fablab-ProtoSpace/OctoPi.git --branch devel-jeroen --single-branch
    cd OctoPi/src
    sudo ./chroot_script

Het script zal nu alle dependencies installeren en de `protospace versie van Octoprint <https://github.com/Fablab-ProtoSpace/OctoPrint/tree/devel-jeroen>`_ clonen.

Belangrijke bestanden
---------------------

``/etc/udev/rules.d/30-octoprint.rules``
    udev rules voor het maken van een link /dev/UM* per Ultimaker.
    Voeg hier het serial nummer van de Ultimaker toe

``/home/pi/.octoprint/config.d/*.yaml``
    Configuratie script per Ultimaker.
    Per configuratie wordt een octoprint instantie gestart.

``/home/pi/scripts/octoPrintDevStart``
    Start voor iedere configuratie in config.d een Octoprint instantie

``/etc/haproxy/haproxy.conf``
    haproxy configuratie file
