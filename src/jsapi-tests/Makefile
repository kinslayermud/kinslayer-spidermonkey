# -*- Mode: makefile -*-
#
# ***** BEGIN LICENSE BLOCK *****
# Version: MPL 1.1/GPL 2.0/LGPL 2.1
#
# The contents of this file are subject to the Mozilla Public License Version
# 1.1 (the "License"); you may not use this file except in compliance with
# the License. You may obtain a copy of the License at
# http://www.mozilla.org/MPL/
#
# Software distributed under the License is distributed on an "AS IS" basis,
# WITHOUT WARRANTY OF ANY KIND, either express or implied. See the License
# for the specific language governing rights and limitations under the
# License.
#
# The Original Code is Spidermonkey build system.
#
# The Initial Developer of the Original Code is
# The Mozilla Foundation.
# Portions created by the Initial Developer are Copyright (C) 2009
# the Initial Developer. All Rights Reserved.
#
# Contributor(s):
#     Jason Orendorff
#
# Alternatively, the contents of this file may be used under the terms of
# either of the GNU General Public License Version 2 or later (the "GPL"),
# or the GNU Lesser General Public License Version 2.1 or later (the "LGPL"),
# in which case the provisions of the GPL or the LGPL are applicable instead
# of those above. If you wish to allow use of your version of this file only
# under the terms of either the GPL or the LGPL, and not to allow others to
# use your version of this file under the terms of the MPL, indicate your
# decision by deleting the provisions above and replace them with the notice
# and other provisions required by the GPL or the LGPL. If you do not delete
# the provisions above, a recipient may use your version of this file under
# the terms of any one of the MPL, the GPL or the LGPL.
#
# ***** END LICENSE BLOCK *****

DEPTH		= ..
topsrcdir	= ..
srcdir		= .
VPATH		= .

include $(DEPTH)/config/autoconf.mk

PROGRAM         = jsapi-tests$(BIN_SUFFIX)
CPPSRCS = \
  tests.cpp \
  selfTest.cpp \
  testPropCache.cpp \
  testXDR.cpp \
  testIntString.cpp \
  testSameValue.cpp \
  testDefineGetterSetterNonEnumerable.cpp \
  $(NULL)

DEFINES         += -DEXPORT_JS_API

LIBS      = $(NSPR_LIBS) $(DEPTH)/$(LIB_PREFIX)js_static.$(LIB_SUFFIX)

LOCAL_INCLUDES += -I$(topsrcdir) -I..

ifdef _MSC_VER
ifdef WINCE
WIN32_EXE_LDFLAGS += -ENTRY:mainACRTStartup
endif
endif

include $(topsrcdir)/config/rules.mk

check::
	$(wildcard $(RUN_TEST_PROGRAM)) $(DIST)/bin/jsapi-tests$(BIN_SUFFIX)
