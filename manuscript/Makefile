
DRAFTS = vorwort-draft.pdf \
	 1-was-ist-openwrt-draft.pdf \
	 1-moeglichkeiten-und-grenzen-draft.pdf \
	 1-alternativen-zu-openwrt-draft.pdf \
         2-aufgaben-paketfilter-draft.pdf \
         2-welche-protokolle-draft.pdf \
	 2-ipv4-fuer-firewall-draft.pdf \
	 2-ipv6-fuer-firewall-draft.pdf \
	 2-gleichzeitig-ipv4-ipv6-draft.pdf \
	 2-icmp-igmp-draft.pdf \
	 2-icmpv6-draft.pdf \
	 2-nat-draft.pdf \
	 3-sysctl-draft.pdf \
	 3-netfilter-kernel-draft.pdf \
	 3-openwrt-luci-draft.pdf \
	 4-anforderungen-draft.pdf \
	 4-testen-draft.pdf \
	 4-dokumentation-draft.pdf \
	 A-analyse-iptables-draft.pdf \
	 A-risikoanalyse-draft.pdf \
#
PANDOCDIR = ../pandoc

%-draft.pdf: %.mdwn
	pandoc -o $@ -H $(PANDOCDIR)/draft.tex $<

all:

clean:
	rm -f *.pdf

drafts: $(DRAFTS)
