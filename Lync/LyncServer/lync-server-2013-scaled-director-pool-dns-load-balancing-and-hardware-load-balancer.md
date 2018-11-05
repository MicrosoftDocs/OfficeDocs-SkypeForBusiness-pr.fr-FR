---
title: "Lync Server 2013 : Pool dir. màé - Éq. de ch. DNS et équilibreur de ch. mat."
TOCTitle: Pool directeur mis à l’échelle - Équilibrage de charge DNS et équilibreur de charge matérielle
ms:assetid: a1f6ffc0-9e6e-4217-a923-025c9679e154
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205142(v=OCS.15)
ms:contentKeyID: 49298408
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Pool directeur mis à l’échelle - Équilibrage de charge DNS et équilibreur de charge matérielle dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-22_

Un pool de directeurs ajusté, qui comporte plus d’un seul directeur déployé pour gérer la capacité supplémentaire et fournir une haute disponibilité, nécessite un équilibrage de la charge afin de distribuer les communications de clients et de serveurs à tous les membres du pool. Un directeur héberge des services web tout comme un pool de serveurs frontaux. Vous pouvez utiliser soit l’équilibrage de la charge matérielle, soit l’équilibrage de la charge DNS (Domain Name System) et l’équilibrage de la charge matérielle. L’équilibrage de la charge matérielle est nécessaire pour les services web et l’équilibrage de la charge DNS seul ne procure pas les fonctionnalités requises pour les services web.

Les rubriques suivantes décrivent les considérations relatives à la planification du déploiement d’un pool de directeurs à l’aide de l’équilibrage de la charge DNS conjointement avec l’équilibrage de la charge matérielle. Si vous envisagez de faire appel à l’équilibrage de la charge matérielle mais pas à l’équilibrage de la charge DNS pour le pool de directeurs, reportez-vous à la rubrique [Pool directeur mis à l’échelle - Équilibreur de charge matérielle dans Lync Server 2013](lync-server-2013-scaled-director-pool-hardware-load-balancer.md), qui décrit les exigences de planification pour cette topologie.

![Pool directeur mis à l'échelle](images/JJ205142.35a78a7a-b781-4c8f-951e-168451ba6a65(OCS.15).jpg "Pool directeur mis à l'échelle")

## Dans cette section

  - [Résumé des certificats - Équilibrage de charge DNS et matérielle dans Lync Server 2013](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [Résumé des ports - Équilibrage de charge DNS et matérielle dans Lync Server 2013](lync-server-2013-port-summary-dns-and-hlb-load-balanced.md)

  - [Résumé des enregistrements DNS - Équilibrage de charge DNS et matérielle dans Lync Server 2013](lync-server-2013-dns-summary-dns-and-hlb-load-balanced.md)

