---
title: "Prise en ch. des certif. comportant des caractères génériques Lync Server 2013"
TOCTitle: Prise en charge des certificats comportant des caractères génériques
ms:assetid: 0bae2aa8-b6dc-46f5-a3be-3fe7581809d4
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Hh202161(v=OCS.15)
ms:contentKeyID: 49296221
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Prise en charge des certificats comportant des caractères génériques dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-03-21_

Lync Server 2013 utilise des certificats pour assurer le cryptage des communications et l’authentification de l’identité du serveur. Dans certains cas, notamment la publication web via le proxy inverse, la saisie d’un autre nom de sujet (SAN) fort correspondant au nom de domaine complet (FQDN) du serveur hébergeant le service n’est pas requise. Dans de tels cas, il est possible d’utiliser des certificats avec des entrées SAN génériques (appelés également certificats génériques) pour réduire le coût d’un certificat exigé par une autorité de certification publique afin de réduire la complexité du processus de planification pour les certificats.

> [!WARNING]  
> Pour conserver les fonctionnalités des périphériques de communications unifiées (UC) tels que les téléphones de bureaux, il est important de tester avec soin le certificat déployé pour garantir le bon fonctionnement des périphériques après avoir implémenté un certificat générique.

Une entrée de certificat n’est pas prise en charge en tant que nom d’objet (aussi appelé nom commun ou CN) pour un rôle donné. Les rôles serveur suivants sont pris en charge lors de l’utilisation d’entrées génériques dans le SAN :

  -   
    **Proxy inverse.** La saisie d’un autre nom de sujet générique est prise en charge pour un certificat de publication d’URL simple (réunions et accès).

  -   
    **Proxy inverse.**   La saisie d’un autre nom de sujet générique est prise en charge pour les entrées SAN de LyncDiscover sur le certificat de publication.

  -   
    **Directeur.** La saisie d’un autre nom de sujet générique est prise en charge pour des URL simples (réunions et accès) et pour les entrées SAN de LyncDiscover et LyncDiscoverInternal dans des composants web Directeur.

  -   
    **serveur frontal ( Standard Edition) et pool de serveurs frontaux ( Enterprise Edition).** La saisie d’un autre nom de sujet générique est prise en charge pour des URL simples (réunions et accès) et pour les entrées SAN de LyncDiscover et LyncDiscoverInternal dans des composants web frontaux.

  -   
    **messagerie unifiée Exchange.** Le serveur n’utilise pas d’entrées SAN lorsqu’il est déployé en tant que serveur autonome.

  -   
    **Microsoft Exchange ServerServeur d’accès client.**   Les entrées génériques du SAN sont prises en charge pour les clients internes et externes.

  -   
    Serveur d’accès client de **messagerie unifiée Exchange et Microsoft Exchange Server sur le même serveur.** Les entrées SAN génériques sont prises en charge.

Rôles serveur non traités dans ce chapitre :

  - Rôles serveurs internes (dont le serveur de médiation, le serveur d’archivage et de surveillance, le Survivable Branch Appliance ou le serveur Survivable Branch Server)

  - Interfaces externes serveur Edge

  - Internes serveur Edge
    
    > [!NOTE]  
    > Pour l’interface interne serveur Edge, une entrée générique peut être affectée au SAN et elle est prise en charge. Le SAN associé au serveur Edge interne n’est pas requis et la valeur d’une entrée SAN générique est limitée.

Pour plus d’informations sur la configuration des certificats, notamment sur l’utilisation des caractères génériques dans les certificats, consultez les rubriques suivantes :

  - [Exigences de certificat pour les serveurs internes dans Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [Certificats requis pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [Résumé des certificats - Équilibrage de charge DNS et matérielle dans Lync Server 2013](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [Résumé des certificats - Directeur unique dans Lync Server 2013](lync-server-2013-certificate-summary-single-director.md)

  - [Résumé des certificats - Pool directeur mis à l’échelle, équilibreur de charge matérielle dans Lync Server 2013](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [Résumé des certificats - Proxy inverse dans Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [Instructions d’intégration de la messagerie unifiée locale et de Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

Pour plus d’informations sur la configuration des certificats pour Exchange, notamment sur l’utilisation des caractères génériques, consultez la documentation d’Exchange 2013.

