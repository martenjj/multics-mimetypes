#########################################################################
#  Project:		Multics MIME Types				#
#  Edit:		17-May-17					#
#########################################################################
#									#
#  Copyright (c) 2017 Jonathan Marten <jjm@keelhaul.me.uk>		#
#  Home & download:  http://github.com/martenjj/multics-mimetypes/	#
#									#
#  This program is free software; you can redistribute it and/or	#
#  modify it under the terms of the GNU General Public License as	#
#  published by the Free Software Foundation;  either version 3 of	#
#  the License, or (at your option) any later version.			#
#									#
#  It is distributed in the hope that it will be useful, but		#
#  WITHOUT ANY WARRANTY; without even the implied warranty of		#
#  MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the	#
#  GNU General Public License for more details.				#
#									#
#  You should have received a copy of the GNU General Public		#
#  License along with this program; see the file LICENSE for further	#
#  details.  If not, see <http://www.gnu.org/licenses/>.		#
#									#
#########################################################################


#########################################################################
#									#
#  Locating and using extra-cmake-modules				#
#									#
#########################################################################

set(ECM_MIN_VERSION "5.0.0")
find_package(ECM ${ECM_MIN_VERSION} REQUIRED NO_MODULE)
set(CMAKE_MODULE_PATH ${ECM_MODULE_PATH} ${ECM_KDE_MODULE_DIR})

#########################################################################
#									#
#  Locating other packages						#
#									#
#########################################################################

include(ECMInstallIcons)
include(KDEInstallDirs)

include(FindSharedMimeInfo)
find_package(SharedMimeInfo REQUIRED)

#########################################################################
#									#
#  Installation of MIME and association files				#
#									#
#########################################################################

install(FILES multics-mime.xml DESTINATION ${KDE_INSTALL_MIMEDIR})
update_xdg_mimetypes(${KDE_INSTALL_MIMEDIR})

#########################################################################
#									#
#  Installation of icons						#
#									#
#########################################################################

set(multics_ICONS 32-mimetypes-multics_file.png
                  48-mimetypes-multics_file.png
                  64-mimetypes-multics_file.png
                  32-mimetypes-multics_archive.png
                  48-mimetypes-multics_archive.png
                  64-mimetypes-multics_archive.png)

ecm_install_icons(ICONS ${multics_ICONS} DESTINATION ${KDE_INSTALL_ICONDIR})
