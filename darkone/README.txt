Darkone Firewall Readme File


#################################################################
#                                                               #
#       Darkone Firewall - Make it easyer as possible           #
#                                                               #
#       Copyright (C) 2010 Alexandru Loredan Stancu             #
#                          loredan.stancu@gmail.com             #
#                                                               #
#################################################################

###########################################
#                                         #
# This file is part of Darkone Firewall.  #
#                                         #
###########################################

#############################################################################
#                                                                           #                                                                     
# Darkone Firewall is free software: you can redistribute it and/or modify  #
# it under the terms of the GNU General Public License as published by      #
# the Free Software Foundation, either version 3 of the License, or         #
# (at your option) any later version.                                       #
#                                                                           #
# Darkone Firewall is distributed in the hope that it will be useful,       #
# but WITHOUT ANY WARRANTY; without even the implied warranty of            #
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the             #
# GNU General Public License for more details.                              #
#                                                                           #
# You should have received a copy of the GNU General Public License         #
# along with this program.  If not, see <http://www.gnu.org/licenses/>.     #
#                                                                           #
#############################################################################



#### INSTALLATION  - for Debian only ####

Step 1

	Untar the darkone-firewall-xxx.tar.gz file. darkone-firewall directory will be created in the current working directory.

Step 2
	Go into darkone-firewall directory: cd darkone-firewall
	Run ./install.sh  as root

Stept 3

	Add configuration files to /etc/darkone/
	
	Note: A configuration file contains rules for the firewall and its name is finished in .conf


#### IMPORTANT ####

	Please read Relese_Notes.txt file and /etc/darkone/firewall.conf file before you start to use this firewall.

#### Modularity ####

Darkone Firewall is modular. That means a new modules 
can be easily added to it. Version 0.10.0 comes with 
only one module: filter. This module is used for traffic
filtering and you can use it by adding "[filter]" in the
rules configuration file(s). Rules configuration files
can be placed in /etc/darkone/ and /etc/darkone/firewall.conf
is mandatory. If you look in that file you'll find a line
which contains "[filter]" keyword. Under that line all
filtering rules are written.

If you want to add a new module to the script you have to
follow the next steps:

Step 1: 

	Choose a name for your module. For example "filter-ng"
	Edit the rules configuration file and add the filter
	name on one line: "[filter-ng]"
	Under this line you write your own rules syntax.
	
Step 2:

	Create a file (bash script) in /opt/darkone/modules/filter-ng
	In this file you'll write all the functiones needed by this module.
	There is only one condition: you must create at least one function
	named "filter-ng ()". This function will be called by the Darkone Firewall.	
