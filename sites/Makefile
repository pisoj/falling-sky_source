################################################################
# Do we permit publishing to rsync.gigo.com and files.gigo.com?#
################################################################
PUBLISH := true

sites:: FORCE parse-sites
ifeq ($(PUBLISH),true)
	@echo checking my hostname
	hostname
	@echo Checking to see what sites are up or down
	./parse-sites --minimum 20
else
	@echo Skipping sites up/down check
endif  

FORCE::


parse-sites: parse-sites.go
	go build parse-sites.go
