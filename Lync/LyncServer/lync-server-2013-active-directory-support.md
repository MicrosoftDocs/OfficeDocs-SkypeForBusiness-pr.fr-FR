---
title: Prise en charge d’Active Directory dans Lync Server 2013
TOCTitle: Prise en charge d’Active Directoryt
ms:assetid: 28ed9ac4-586d-4803-ad45-99c4fa793f54
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425756(v=OCS.15)
ms:contentKeyID: 49296683
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Prise en charge d’Active Directory dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Les topologies locales des services de domaine Active Directory prises en charge par Lync Server 2013 sont les suivantes :

  - Forêt unique avec domaine unique

  - Forêt unique avec un arbre unique et plusieurs domaines

  - Forêt unique avec plusieurs arbres et des espaces de noms disjoints

  - Plusieurs forêts dans une topologie de forêt centrale

  - Plusieurs forêts dans une topologie de forêt de ressources

> [!NOTE]  
> Le Lync Server 2013 ne prend pas en charge les domaines en une seule partie. Par exemple, une forêt comportant le domaine racine <strong>contoso.local</strong> est prise en charge, alors que le domaine racine <strong>local</strong> en une seule partie ne l’est pas. Pour plus d’informations, reportez-vous à l’article 300684 de la base de connaissances Microsoft, « Informations sur la configuration des domaines Active Directory à l’aide de noms DNS en une seule partie », à l’adresse <a href="http://go.microsoft.com/fwlink/p/?linkid=143752">http://go.microsoft.com/fwlink/p/?linkId=143752</a>.

> [!NOTE]  
> Lync Server 2013 ne prend pas en charge l’attribution de nouveau nom aux domaines. Si vous devez renommer un domaine où Lync Server est déployé, vous devez d’abord désinstaller Lync Server, renommer le domaine, puis réinstaller Lync Server.

Pour plus d’informations sur les topologies prises en charge et les conditions requises des déploiements locaux, reportez-vous à [Configuration requise, prise en charge et topologies relatives aux services de domaine Active Directory dans Lync Server 2013](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md) dans la documentation de planification.

