---
title: Configuration de la prise en charge de la découverte automatique
TOCTitle: Configuration de la prise en charge de la découverte automatique
ms:assetid: 3a266456-69a0-4539-ba99-d388b83799a8
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ945622(v=OCS.15)
ms:contentKeyID: 53095397
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de la prise en charge de la découverte automatique

 

_**Dernière rubrique modifiée :** 2016-12-08_

Les services web Lync Server**Service de découverte automatique** sont apparus pour la première fois dans la mise à jour cumulative Lync Server 2010 de novembre 2011. Cette mise à jour était accompagnée de la version initiale des clients Lync Mobile. Le service de découverte automatique exposait les services de mobilité, également connus sous le nom de service Mcx.

Le service de découverte automatique constitue un emplacement unique à partir duquel tous les clients peuvent demander des informations sur la disponibilité d’un service ou d’une fonctionnalité spécifique et sur la façon de contacter les services – par le biais d’un nom de domaine complet ou d’une référence à une URL web. La découverte automatique expose de nombreuses fonctionnalités, et chaque client effectue des demandes en fonction des fonctionnalités qu’il peut utiliser. Par exemple, un client Lync 2013 de bureau peut utiliser la découverte automatique pour déterminer les services web externes, mais n’utilisera pas les services de mobilité (Mcx). Pour définir et activer correctement vos clients afin qu’ils utilisent les fonctionnalités mises à leur disposition, vous devez définir les scénarios qui permettent à un client de rechercher et d’utiliser efficacement des entrées de découverte automatique. Pour utiliser la découverte automatique dans le cadre de votre déploiement, il est nécessaire qu’un proxy inverse publie les services web Lync Server, que des enregistrements DNS soient configurés pour résoudre les requêtes DNS liées au service de découverte automatique Lync Server et aux services web Lync Server et que les services de certificat soient correctement configurés pour votre scénario.

> [!TIP]  
> Pour obtenir des détails techniques sur les tâches effectuées par les éléments de la demande/réponse de découverte automatique, voir <a href="lync-server-2013-understanding-autodiscover.md">Présentation de la découverte automatique</a>.

Les informations et tableaux suivants définissent, par scénario, les configurations que vous devez éventuellement implémenter pour que le service de découverte automatique soit pleinement exploitable. Les informations des rubriques suivantes sont propres à Microsoft Lync Server 2013. Pour obtenir de l’aide sur la planification de la mobilité pour Lync Server 2010, voir <http://go.microsoft.com/fwlink/?linkid=275113>. Pour déployer la mobilité pour Lync Server 2010, voir <http://go.microsoft.com/fwlink/?linkid=275114>.

## Dans cette section

  - [Configuration du DNS pour la découverte automatique](lync-server-2013-configuring-dns-for-autodiscover.md)

  - [Configuration des certificats pour la découverte automatique](lync-server-2013-configuring-certificates-for-autodiscover.md)

  - [Configuration d’un proxy inverse pour la découverte automatique](lync-server-2013-configuring-a-reverse-proxy-for-autodiscover.md)

  - [Configuration de la découverte automatique pour les déploiements hybrides](lync-server-2013-configuring-autodiscover-for-hybrid-deployments.md)

