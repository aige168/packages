#
# Copyright (C) Alexandru Ardelean <ardeleanalex@gmail.com>
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=django
PKG_VERSION:=5.1.7
PKG_RELEASE:=1

PYPI_NAME:=Django
PKG_HASH:=30de4ee43a98e5d3da36a9002f287ff400b43ca51791920bfb35f6917bfe041c

PKG_MAINTAINER:=Alexandru Ardelean <ardeleanalex@gmail.com>, Peter Stadler <peter.stadler@student.uibk.ac.at>
PKG_LICENSE:=BSD-3-Clause
PKG_LICENSE_FILES:=LICENSE LICENSE.python
PKG_CPE_ID:=cpe:/a:djangoproject:django

include ../pypi.mk
include $(INCLUDE_DIR)/package.mk
include ../python3-package.mk

define Package/python3-django
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=The web framework for perfectionists with deadlines.
  URL:=https://www.djangoproject.com/
  DEPENDS:= +python3 +python3-pytz +python3-sqlparse +python3-asgiref
  CONFLICTS:=python3-django1
  PROVIDES:=django
endef

define Package/python3-django/description
    The web framework for perfectionists with deadlines.
endef

define Py3Package/python3-django/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/django-admin $(1)/usr/bin
endef

$(eval $(call Py3Package,python3-django))
$(eval $(call BuildPackage,python3-django))
$(eval $(call BuildPackage,python3-django-src))
