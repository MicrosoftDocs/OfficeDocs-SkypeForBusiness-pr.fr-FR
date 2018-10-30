---
title: 'Lync Server 2013 : Instructions de déploiement de Voix Entreprise'
TOCTitle: Instructions de déploiement de Voix Entreprise
ms:assetid: 8985bd93-7613-4cef-9c89-51df6049ed9b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398694(v=OCS.15)
ms:contentKeyID: 49297997
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Instructions de déploiement de Voix Entreprise dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-21_

Cette rubrique décrit les conditions préalables requises et autres directives dont vous devez tenir compte lorsque vous planifiez de déployer Lync Server 2013 et la charge de travail Voix Entreprise.

## Conditions préalables requises pour le déploiement

Pour que le déploiement de Voix Entreprise se déroule dans les meilleures conditions possibles, vérifiez que l’infrastructure, le réseau et les systèmes informatiques remplissent les conditions préalables ci-dessous :

  - Lync Server 2013 Standard Edition ou Enterprise Edition est installé et opérationnel sur votre réseau.

  - Tous les serveurs Edge sont déployés et opérationnels dans votre réseau de périmètre, y compris les serveurs Edge avec le service Edge d’accès, le service Edge A/V, le service Edge de conférence web et un proxy inverse.

  - Un ou plusieurs utilisateurs ont été créés et activés pour Lync Server.

  - Microsoft Exchange Server 2007 Service Pack 1 (SP1) (ou dernier Service Pack) ou Microsoft Exchange Server 2010 est installé. L’un ou l’autre est nécessaire pour l’intégration de la messagerie unifiée Exchange avec Lync Server et pour fournir des notifications enrichies et des informations de journal d’appels aux points de terminaison clients.

  - Un numéro de téléphone principal unique a été désigné, normalisé et copié dans l’attribut **msRTCSIP-line** pour chaque utilisateur devant être activé pour Voix Entreprise.
    
    > [!NOTE]  
    > Lync Server prend en charge les numéros E.164 ainsi que les numéros non DID (Direct Inward Dialing). Les numéros non DID peuvent être représentés au format <strong>&lt;E.164&gt;;ext=&lt;extension&gt;</strong> ou comme une chaîne de chiffres, mais le numéro de poste privé doit être unique dans l’entreprise. Par exemple, le numéro privé 1 001 peut être représenté comme suit : <strong>+1425550100;ext=1001</strong> ou <strong>1001</strong>. S’il est représenté comme <strong>1001</strong>, ce numéro privé doit être unique dans l’entreprise.

  - Les administrateurs déployant Voix Entreprise doivent être membres du groupe RTCUniversalServerAdmins.

  - Au minimum, Office Communicator 2007 est déployé avec succès. Pour utiliser les nouvelles fonctionnalités de cette version, Lync 2013 est déployé.

  - L’infrastructure MKI (Managed key infrastructure) est déployée et configurée, à l’aide d’une infrastructure d’autorité de certification Microsoft ou tierce.

  - Chaque ordinateur sur lequel vous installez un serveur de médiation doit :
    
      - Être un serveur membre d’un domaine et être préparé pour les services de domaine Active Directory. Pour plus d’informations sur les procédures de préparation des services de domaine Active Directory, reportez-vous à [Préparation des services de domaine Active Directory pour Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) dans la documentation de déploiement.
    
      - Exécuter l’un des systèmes d’exploitation suivants :
        
          -   
            Édition 64 bits du système d’exploitation Windows Server 2008 Standard
        
          -   
            Édition 64 bits du système d’exploitation Windows Server 2008 Enterprise

  - Si la connexion au réseau téléphonique commuté (RTC) ou à l’autocommutateur privé (PBX) s’effectue au moyen d’une connexion TDM (multiplexage temporel), une ou plusieurs passerelles RTC sont disponibles pour le déploiement. (Si la connexion s’effectue via une jonction SIP, une passerelle RTC n’est pas nécessaire.)

## Coupure de courant, interruption du réseau ou du service téléphonique

En cas de coupure d’électricité et de perturbation ou dégradation des services réseau ou téléphoniques, le système vocal et les fonctionnalités de messagerie instantanée, de présence et autres fonctions de Lync Server ainsi que tout périphérique connecté à Lync Server peuvent ne pas fonctionner correctement.

## Voix Entreprise dépend de la disponibilité du serveur et de l’opérabilité du client et du matériel vocal

Les communications vocales à l’aide de Lync Server dépendent de la disponibilité du logiciel serveur et du bon fonctionnement des clients vocaux ou des périphériques téléphoniques matériels connectés au logiciel serveur.

## Méthode alternative d’accès aux services d’urgence

Lorsque vous installez un client vocal (par exemple, un PC exécutant un client Lync ou un appareil Lync Phone Edition), il est recommandé de conserver une solution de secours pour permettre aux utilisateurs d’appeler les services d’urgence (18, 112, etc.) en cas de coupure de courant, de dégradation de la connectivité réseau, d’interruption du service téléphonique ou d’autres problèmes pouvant limiter le fonctionnement de périphériques Lync Server, Lync, ou Lync Phone Edition. Une telle alternative peut consister en un téléphone connecté à une ligne de réseau téléphonique commuté (RTC) standard ou un téléphone mobile.

## Appels d’urgence et systèmes téléphoniques multilignes

L’utilisation d’un système téléphonique multiligne (MLTS) peut être sujette à une réglementation d’état et/ou fédérale des États-Unis et à une réglementation étrangère relative aux systèmes téléphoniques multilignes exigeant du système qu’il fournisse le numéro de téléphone ou de poste et/ou l’emplacement physique de l’appelant aux services d’urgence appropriés lorsqu’un appel est effectué (par exemple, lorsque le numéro d’un service d’urgence, tel que le 18 ou le 112, est composé). Dans cette version, Lync Server peut être configuré pour fournir la position géographique d’un appelant à un fournisseur de services d’urgence, comme indiqué dans [Planification des services d’urgence (E9-1-1) dans Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md). Le respect des réglementations MLTS est l’unique responsabilité de l’acquéreur de Lync Server, du client Lync, et d’appareils Lync Phone Edition.

