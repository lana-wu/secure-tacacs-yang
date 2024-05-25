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
area: "Operations and Management"
workgroup: "Operations and Management Area Working Group"
keyword:
 - XXXX
 - XXXX
 - XXXX
venue:
  group: "Operations and Management Area Working Group"
  type: "Working Group"
  mail: "opsawg@ietf.org"
  arch: "https://mailarchive.ietf.org/arch/browse/opsawg/"
  github: "boucadair/secure-tacacs-yang"
  latest: "https://boucadair.github.io/secure-tacacs-yang/draft-boucadair-opsawg-secure-tacacs-yang.html"

author:
 -
    fullname: Mohamed Boucadair
    organization: Orange
    role: editor
    email: mohamed.boucadair@orange.com
    
    fullname: Bo Wu
    organization: Huawei technology
    role: editor
    email: lana.wubo@huawei.com    

normative:

informative:


--- abstract

This document defines a YANG module for Terminal Access Controller Access-Control System Plus (TACACS+) over TLS 1.3. This modules augments the YANG Data Model for Terminal Access Controller Access-Control System Plus (TACACS+) defined in the RFC 9105 with TLS-related data nodes.

--- middle

# Introduction

This document defines a YANG module for managing Terminal Access Controller Access-Control System Plus (TACACS+) over TLS 1.3 {{!I-D.ietf-opsawg-tacacs-tls13}}. The module is designed as an augmentation to the "ietf-system-tacacs-plus" module specified in {{!RFC9105}}.

The module leverages the TLS structures defined in {{!I-D.ietf-netconf-tls-client-server}}.

This first version of the specification uses a pruning approach rather that a reuse of the groupings defined in {{!I-D.ietf-netconf-tls-client-server}}.

> Discussion Note: RFC 9105bis or keep the current augment design.

# Conventions and Definitions

{::boilerplate bcp14-tagged}

The meanings of the symbols in the YANG tree diagrams are defined in {{?RFC8340}}.

The document uses the terms defined in {{Section 2 of !I-D.ietf-opsawg-tacacs-tls13}} and {{Section 3 of ?RFC8907}}.

> Note to the RFC Editor: Please update the following:
>
>  *  AAAA --> the assigned RFC number for {{!I-D.ietf-netconf-crypto-types}}
>  *  BBBB --> the assigned RFC number for {{!I-D.ietf-netconf-trust-anchors}}
>  *  CCCC --> the assigned RFC number for {{!I-D.ietf-netconf-keystore}}
>  *  FFFF --> the assigned RFC number for {{!I-D.ietf-netconf-tls-client-server}}
>  *  XXXX --> the assigned RFC number for this document.

# Module Tree Structure

The full tree structure is shown below:

~~~~~~~~~~
{::include-fold ./trees/full-tree.txt}
~~~~~~~~~~

# YANG Module

This module uses types and groupings defined in {{!RFC6991}}, {{!RFC8341}}, {{!I-D.ietf-netconf-crypto-types}}, {{!I-D.ietf-netconf-trust-anchors}},
{{!I-D.ietf-netconf-keystore}}, and {{!I-D.ietf-netconf-tls-client-server}}.

The modules also cites {{!RFC9257}}, {{!RFC9258}}, {{!RFC9258}}, and {{!RFC6520}}.

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

   This YANG module uses groupings from other YANG modules that
   define nodes that may be considered sensitive or vulnerable
   in network environments. Refer to {{Section 5.3 of !I-D.ietf-netconf-tls-client-server}} for information as to which nodes may
   be considered sensitive or vulnerable in network environments.

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
   Name:  ietf-system-secure-tacacs
   Namespace:  urn:ietf:params:xml:ns:yang:ietf-system-secure-tacacs
   Prefix:  secure-tacacs
   Maintained by IANA?  N
   Reference:  RFC XXXX
~~~~


--- back

# Acknowledgments
{:numbered="false"}

TODO acknowledge.
