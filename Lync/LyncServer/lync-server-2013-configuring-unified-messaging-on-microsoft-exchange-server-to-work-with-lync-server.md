---
title: "LS 2013 : Conf. mess. un. sur Microsoft Exchange Server pour fonct. avec LS"
TOCTitle: Configuration de la messagerie unifiée sur Microsoft Exchange Server de sorte qu’elle fonctionne avec Lync Server 2013
ms:assetid: 058da9c4-23af-4ddb-9f63-70133a8aafc6
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398106(v=OCS.15)
ms:contentKeyID: 49296125
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de la messagerie unifiée sur Microsoft Exchange Server de sorte qu’elle fonctionne avec Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

> [!IMPORTANT]  
> Si vous souhaitez utiliser la messagerie unifiée Exchange pour offrir aux utilisateurs de Voix Entreprise les services Répondeur automatique, Standard automatique et Outlook Voice Access, lisez <a href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">Planification de l’intégration de la messagerie unifiée Exchange dans Lync Server 2013</a> dans la documentation de planification, puis suivez les instructions de cette section.

Pour configurer la messagerie unifiée Exchange afin qu’elle fonctionne avec Voix Entreprise, vous devez effectuer les tâches suivantes :

  - Configurer des certificats sur le serveur exécutant les services de la messagerie unifiée Exchange
    
    > [!NOTE]  
    > Ajoutez tous les serveurs d’accès au client et de boîte aux lettres à tous les plans de numérotation URI SIP de messagerie unifiée. Autrement, le routage des appels sortant ne fonctionnera pas correctement.

  - Créez un ou plusieurs plans de numérotation URI SIP de messagerie unifiée ainsi que, le cas échéant, leurs numéros d’accès d’abonné, puis créez les plans de numérotation Lync Server correspondants

  - Utilisez le script **exchucutil.ps1** pour :
    
      - créer des passerelles IP de messagerie unifiée ;
    
      - créer des groupements de postes de messagerie unifiée ;
    
      - octroyer des autorisations Lync Server 2013 pour lire des objets de services de domaine Active Directory de messagerie unifiée ;

  - créer un objet de standard automatique de messagerie unifiée ;

  - créer un objet accès d’abonné ;

  - créer un URI SIP pour chaque utilisateur et associer des utilisateurs à un plan de numérotation URI SIP de messagerie unifiée.

## Conditions requises et recommandations

Avant de commencer, la documentation dans cette section suppose que vous avez déployé les rôles Exchange 2013 suivants : accès au client et boîte aux lettres. Dans Microsoft Exchange Server 2013, la messagerie unifiée Exchange s’exécute en tant que service sur ces serveurs.

Pour plus d’informations sur le déploiement de Exchange 2013, reportez-vous à Exchange 2013 dans la bibliothèque TechNet, à l’adresse [http://go.microsoft.com/fwlink/p/?LinkId=266637](http://go.microsoft.com/fwlink/p/?linkid=266637)

Notez également les points suivants :

  - Si messagerie unifiée Exchange est installé dans plusieurs forêts, vous devez effectuer les étapes d’intégration d’Exchange Server pour chaque forêt de messagerie unifiée, qui doit être configurée pour approuver la forêt où Lync Server 2013 est déployé, elle-même devant l’être pour approuver chaque forêt de messagerie unifiée.Lync Server 2013

  - Les étapes d’intégration s’effectuent sur les rôles serveur Exchange qui exécutent les services de messagerie unifiée, ainsi que sur le serveur qui exécute Lync Server 2013. Vous devez effectuer les étapes d’intégration de la messagerie unifiée Exchange Server avant de procéder à l’intégration de Lync Server 2013.
    
    > [!NOTE]  
    > Pour voir quelles étapes d’intégration sont effectuées sur quels serveurs et par quels rôles d’administrateur, reportez-vous à <a href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Processus de déploiement pour l’intégration de la messagerie unifiée locale et de Lync Server 2013</a>.

Les outils suivants doivent être disponibles sur chaque serveur qui exécute la messagerie unifiée Exchange:

  - Environnement de ligne de commande Exchange Management Shell

  - Le script **exchucutil.ps1**, exécute les tâches suivantes :
    
      - Il crée une passerelle IP de messagerie unifiée pour chaque serveur Lync Server 2013.
    
      - Il crée un groupement de postes pour chaque passerelle. L’identificateur pilote de chaque groupement de postes spécifie le plan de numérotation URI SIP de messagerie unifiée utilisé par le pool de serveurs frontaux ou le serveur Standard Edition associé à la passerelle.
    
      - Il octroie les autorisations Lync Server 2013 pour lire les objets de messagerie unifiée Exchange dans les services de domaine Active Directory.

## Dans cette section

  - [Configurer les certificats sur le serveur exécutant la messagerie unifiée Microsoft Exchange Server](lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md)

  - [Configurer la messagerie unifiée sur Microsoft Exchange pour Lync Server 2013](lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md)

