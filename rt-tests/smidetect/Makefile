# ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
#
#   Copyright (c) 2019 Red Hat, Inc.
#
#   This program is free software: you can redistribute it and/or
#   modify it under the terms of the GNU General Public License as
#   published by the Free Software Foundation, either version 2 of
#   the License, or (at your option) any later version.
#
#   This program is distributed in the hope that it will be
#   useful, but WITHOUT ANY WARRANTY; without even the implied
#   warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR
#   PURPOSE.  See the GNU General Public License for more details.
#
#   You should have received a copy of the GNU General Public License
#   along with this program. If not, see http://www.gnu.org/licenses/.
#
# ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

export TEST        := rt-tests/smidetect
export TESTVERSION := 1.0

.PHONY: all run clean

# data files, .c files, scripts anything needed to either compile the test and/or run it.
FILES := $(METADATA) runtest.sh Makefile PURPOSE 

build:
	chmod a+x ./runtest.sh

run: $(FILES) build
	./runtest.sh

clean:
	rm -f *~ $(METADATA) *.rpm

# Include Common Makefile
include /usr/share/rhts/lib/rhts-make.include

$(METADATA): Makefile
	@touch $(METADATA)
	@echo "Owner:		Clark Williams <williams@redhat.com>" > $(METADATA)
	@echo "Name:		$(TEST)"	>> $(METADATA)
	@echo "Path:		$(TEST_DIR)"	>> $(METADATA)
	@echo "TestVersion:	$(TESTVERSION)"	>> $(METADATA)
	@echo "License:		GPLv2"		>> $(METADATA)
	@echo "Description:	Test to detect System Management Interrupts (SMIs)" >> $(METADATA)
	@echo "Architectures:	x86_64" >> $(METADATA)
	@echo "TestTime:	1h"	>> $(METADATA)
	@echo "repoRequires:	rt-tests/include"  >> $(METADATA)

	rhts-lint $(METADATA)
