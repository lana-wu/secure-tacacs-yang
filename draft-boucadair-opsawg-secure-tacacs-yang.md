---
title: "A YANG Model for Terminal Access Controller Access-Control System Plus (TACACS+) over TLS 1.3"
abbrev: "YANG for TACACS+ over TLS"
category: info

docname: draft-boucadair-opsawg-secure-tacacs-yang-latest
submissiontype: IETF  # also: "independent", "editorial", "IAB", or "IRTF"
number:
date:
consensus: true
v: 3
area: AREA
workgroup: WG Working Group
keyword:
 - next generation
 - unicorn
 - sparkling distributed ledger
venue:
  group: WG
  type: Working Group
  mail: WG@example.com
  arch: https://example.com/WG
  github: USER/REPO
  latest: https://example.com/LATEST

author:
 -
    fullname: Mohamed Boucadair
    organization: Orange
    role: editor
    email: mohamed.boucadair@orange.com

normative:

informative:


--- abstract

This document defines a YANG module for Terminal Access Controller Access-Control System Plus (TACACS+) over TLS 1.3.


--- middle

# Introduction

TODO Introduction


# Conventions and Definitions

{::boilerplate bcp14-tagged}

# Module Tree Structure

# YANG Module

This module uses references defined in XXXX.

~~~~~~~~~~
<CODE BEGINS> file "ietf-system-secure-tacacs@2024-05-23.yang"
{::include-fold ./yang/ietf-system-secure-tacacs.yang}
<CODE ENDS>
~~~~~~~~~~


# Security Considerations

This section uses the template described in Section 3.7 of {{?I-D.ietf-netmod-rfc8407bis}}.

   The YANG module specified in this document defines schema for data
   that is designed to be accessed via network management protocols such
   as NETCONF {{!RFC6241}} or RESTCONF {{!RFC8040}}.  The lowest NETCONF layer
   is the secure transport layer, and the mandatory-to-implement secure
   transport is Secure Shell (SSH) {{!RFC6242}}.  The lowest RESTCONF layer
   is HTTPS, and the mandatory-to-implement secure transport is TLS
   {{!RFC8446}}.

   The Network Configuration Access Control Model (NACM) {{!RFC8341}}
   provides the means to restrict access for particular NETCONF or
   RESTCONF users to a preconfigured subset of all available NETCONF or
   RESTCONF protocol operations and content.

   There are a number of data nodes defined in this YANG module that are
   writable/creatable/deletable (i.e., config true, which is the
   default).  These data nodes may be considered sensitive or vulnerable
   in some network environments.  Write operations (e.g., edit-config)
   and delete operations to these data nodes without proper protection
   or authentication can have a negative effect on network operations.
   Specifically, the following subtrees and data nodes have particular
   sensitivities/vulnerabilities:

   'xxx':
   :  xxxx.

   Some of the readable data nodes in this YANG module may be considered
   sensitive or vulnerable in some network environments.  It is thus
   important to control read access (e.g., via get, get-config, or
   notification) to these data nodes.  Specifically, the following
subtrees and data nodes have particular sensitivities/vulnerabilities:

   'xxx':
   :  xxxx.


# IANA Considerations

   IANA is requested to register the following URI in the "ns" subregistry within
   the "IETF XML Registry" {{!RFC3688}}:

~~~~
   URI:  urn:ietf:params:xml:ns:yang:ietf-system-secure-tacacs
   Registrant Contact:  The IESG.
   XML:  N/A; the requested URI is an XML namespace.
~~~~

   IANA is requested to register the following YANG module in the "YANG Module
   Names" registry {{!RFC6020}} within the "YANG Parameters" registry group:

~~~~
   Name:  ietf-ac-glue
   Namespace:  urn:ietf:params:xml:ns:yang:ietf-system-secure-tacacs
   Prefix:  secure-tacacs
   Maintained by IANA?  N
   Reference:  RFC XXXX
~~~~


--- back

# Acknowledgments
{:numbered="false"}

TODO acknowledge.
