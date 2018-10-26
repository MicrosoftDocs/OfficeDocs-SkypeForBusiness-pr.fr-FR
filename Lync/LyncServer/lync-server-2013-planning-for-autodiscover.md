---
title: Planification de la découverte automatique
TOCTitle: Planification de la découverte automatique
ms:assetid: 51f1ff94-1d64-4e6d-a878-b86fa07edc2d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ945628(v=OCS.15)
ms:contentKeyID: 53095421
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planification de la découverte automatique

 

_**Dernière rubrique modifiée :** 2013-02-16_

La découverte automatique a été introduite pour Lync Server dans la mise à jour cumulative pour Lync Server 2010 de novembre 2011. La principale finalité de cette implémentation initiale de la découverte automatique était de permettre à Lync Mobile de localiser le service de mobilité (Mcx). Le service de découverte automatique dans Lync Server 2013 est désormais un service utilisé par tous les clients pour la localisation des services serveur et utilisateur. Le service de découverte automatique Microsoft Lync Server 2013 s’exécute sur les directeurs et les serveurs frontaux.

> [!TIP]  
> Pour plus d’informations techniques sur la découverte automatique et sur les éléments communiqués aux clients, voir <a href="lync-server-2013-understanding-autodiscover.md">Présentation de la découverte automatique</a>.<br />
La mobilité demeure un scénario spécifique et les services de mobilité nécessitent une planification particulière. Pour plus d’informations, voir <a href="lync-server-2013-planning-for-mobility.md">Planification de la mobilité dans Lync Server 2013</a>.

Quand la découverte automatique a été introduite dans Lync Server 2010, la solution adoptée devait permettre d’implémenter un service impliquant la modification éventuelle des certificats dans les déploiements de serveur existants. La découverte automatique pouvait être utilisée via le port TCP 443 pour HTTPS ou le port TCP 80 pour HTTP. S’il était décidé d’utiliser HTTPS, les certificats sur les proxys inverses, les directeurs et les serveurs frontaux devaient être réémis afin de permettre la prise en charge des enregistrements DNS `lyncdiscover.<domain>` et `lyncdiscoverinternal.<domain>` requis. S’il était décidé d’utiliser HTTP, la réémission de certificats pouvait être évitée grâce au recours à des enregistrements (ou alias) CNAME DNS pour utiliser des noms existants sur les certificats. L’utilisation de HTTP ne signifiait pas que les communications initiales étaient non chiffrées.

Étant donné que Lync Server 2013 utilise la découverte automatique pour tous les clients, le principal scénario consiste à utiliser HTTPS exclusivement et à créer des certificats avec lyncdiscover.\<domain\> dans le cadre de la configuration des proxys inverses, des directeurs et des serveurs frontaux. Si vous implémentez la découverte automatique dans un déploiement mis à niveau à partir de Lync Server 2010, vous pouvez utiliser HTTP pour éviter la réémission de certificats. Les sections suivantes fournissent de l’aide pour les deux scénarios.

> [!IMPORTANT]  
> La liste des autres noms de sujet sur les certificats utilisés par la règle de publication des services web externes doit contenir une entrée <em>lyncdiscover.&lt;sipdomain&gt;</em> pour chaque domaine SIP situé au sein de votre organisation. Pour plus d’informations sur les entrées des autres noms de sujet requises pour les directeurs, les serveurs frontaux et les proxys inverses, voir <a href="lync-server-2013-certificate-summary-autodiscover.md">Résumé des certificats - découverte automatique</a>.

## Dans cette section

  - [Résumé des certificats - découverte automatique](lync-server-2013-certificate-summary-autodiscover.md)

  - [Synthèse des ports - Découverte automatique dans Lync Server 2013](lync-server-2013-port-summary-autodiscover.md)

  - [Synthèse DNS - Découverte automatique dans Lync Server 2013](lync-server-2013-dns-summary-autodiscover.md)

  - [Hybride et domaine partagé - Découverte automatique](lync-server-2013-hybrid-and-split-domain-autodiscover.md)

