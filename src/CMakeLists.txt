
set(NODOGSPLASH_SRC
	auth.c client_list.c commandline.c
	conf.c debug.c firewall.c
	fw_iptables.c gateway.c http_microhttpd.c
	http_microhttpd_utils.c ndsctl_thread.c
	safe.c tc.c template.c util.c)

set(NDSCTL_SRC ndsctl.c)

add_executable(nodogsplash ${NODOGSPLASH_SRC})
target_link_libRARIES(nodogsplash ${LIBS})

add_executable(ndsctl ${NDSCTL_SRC})
