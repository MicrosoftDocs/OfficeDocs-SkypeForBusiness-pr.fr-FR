---
title: 'Lync Server 2013 : Prise en charge des services de domaine Active Directory'
TOCTitle: Prise en charge des services de domaine Active Directory
ms:assetid: aeb62d5e-e424-473a-b795-9452150c98dd
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412831(v=OCS.15)
ms:contentKeyID: 49298518
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Prise en charge des services de domaine Active Directory dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Lync Server 2013 utilise le magasin central de gestion pour le stockage des données de configuration des serveurs et des services, au lieu de dépendre des services de domaine Active Directory pour ces données, comme par le passé. Lync Server 2013 stocke toujours les éléments suivants dans les services de domaine Active Directory (AD DS) :

  - **Extensions de schéma**
    
      - Extensions de l’objet utilisateur
    
      - Extensions pour les classes Lync Server 2010 et Office Communications Server 2007 R2 afin de conserver la compatibilité descendante avec les versions prises en charge précédentes

  - **Données** (stockées dans le schéma étendu de Lync Server 2013 et dans les classes existantes)
    
      - URI SIP de l’utilisateur et autres paramètres utilisateur
    
      - Objets contact pour les applications (par exemple, l’application Response Group et l’application Intendant Conférence)
    
      - Données publiées pour la compatibilité descendante
    
      - Un point de contrôle du service (SCP) pour le magasin central de gestion
    
      - Compte d’authentification Kerberos (un objet ordinateur facultatif)

Cette section décrit les conditions requises pour la prise en charge des services de domaine Active Directory pour Lync Server 2013. Pour plus d’informations sur la prise en charge de la topologie, reportez-vous à [Topologies Active Directory prises en charge dans Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) dans la documentation de prise en charge.

## Systèmes d’exploitation de contrôleur de domaine pris en charge

Lync Server 2013 prend en charge les contrôleurs de domaine exécutant les systèmes d’exploitation suivants :

  - Système d’exploitation Windows Server 2012 R2

  - Système d’exploitation Windows Server 2012

  - système d’exploitation Windows Server 2008 R2

  - système d’exploitation Windows Server 2008

  - Windows Server 2008 Enterprise 32 bits

  - Les versions 32 bits ou 64 bits du système d’exploitation Windows Server 2003 R2

  - Les versions 32 bits ou 64 bits du système d’exploitation Windows Server 2003

## Niveau fonctionnel des forêts et des domaines

Vous devez élever tous les domaines dans lesquels vous déployez Lync Server 2013 à un niveau fonctionnel de domaine de Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 ou au minimum Windows Server 2003.

Vous devez élever toutes les forêts dans lesquelles vous déployez Lync Server 2013 à un niveau fonctionnel de forêt de Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 ou au minimum Windows Server 2003.

## Prise en charge des contrôleurs de domaine en lecture seule

Lync Server 2013 prend en charge les déploiements des services de domaine Active Directory qui incluent des contrôleurs de domaine en lecture seule ou des serveurs de catalogue global en lecture seule, tant que des contrôleurs de domaine accessibles en écriture sont disponibles.

## Noms de domaine

Lync Server ne prend pas en charge les domaines en une seule partie. Par exemple, une forêt comportant le domaine racine **contoso.local** est prise en charge alors que le domaine racine **local** ne l’est pas. Pour plus d’informations, reportez-vous à l’article 300684 de la base de connaissances Microsoft, « Informations sur la configuration des domaines Active Directory à l’aide de noms DNS en une seule partie », à l’adresse <http://go.microsoft.com/fwlink/?linkid=143752>.

> [!NOTE]  
> Lync Server ne prend pas en charge l’attribution de nouveau nom aux domaines. Si vous devez renommer un domaine où Lync Server est déployé, vous devez d’abord désinstaller Lync Server, renommer le domaine, puis réinstaller Lync Server.

## Environnements de services de domaine Active Directory verrouillés

Dans un environnement de services de domaine Active Directory verrouillé, les objets utilisateur et ordinateur sont souvent placés dans des unités d’organisation spécifiques dans lesquelles l’héritage des autorisations a été désactivé afin de sécuriser la délégation d’administration et de permettre l’utilisation d’objets de stratégie de groupe pour l’application de stratégies de sécurité. Lync Server 2013 peut être déployé dans un environnement Active Directory verrouillé. Pour plus d’informations sur la configuration requise pour le déploiement de Lync Server dans un environnement verrouillé, reportez-vous à [Préparation des services de domaine Active Directory verrouillés dans Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) dans la documentation de déploiement.

