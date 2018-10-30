---
title: Activation ou désactivation de l’intégration avec le stockage Exchange
TOCTitle: Activation ou désactivation de l’intégration avec le stockage Exchange
ms:assetid: c08b9ba5-04f6-452a-b44c-c130f1564a34
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205228(v=OCS.15)
ms:contentKeyID: 49298717
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Activation ou désactivation de l’intégration avec le stockage Exchange

 

_**Dernière rubrique modifiée :** 2012-10-09_

Dans le Panneau de configuration Lync Server 2013, utilisez les configurations d’archivage pour activer ou désactiver l’intégration avec le stockage Exchange. Cela inclut les configurations d’archivage suivantes :

  - Configuration globale qui est créée par défaut lorsque vous déployez Lync Server 2013.

  - Configurations facultatives au niveau d’un site ou d’un pool que vous pouvez créer et utiliser pour spécifier le type d’archivage à implémenter pour un site ou un pool spécifique.

Pour plus d’informations sur l’implémentation des configurations de l’archivage, notamment sur les options disponibles et la hiérarchie des configurations de l’archivage, voir [Fonctionnement de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, dans la documentation de déploiement ou dans la documentation des opérations.

## Pour activer ou désactiver l’intégration avec le stockage Microsoft Exchange

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Configuration d’archivage**.

4.  Cliquez sur le nom de la configuration globale, de site ou de pool appropriée dans la liste des configurations de l’archivage, cliquez sur **Modifier**, cliquez sur **Afficher les détails**, puis effectuez l’une des opérations suivantes :
    
      - Pour activer l’intégration avec le stockage Exchange 2013, activez la case à cocher **Intégration de Microsoft Exchange**.
    
      - Pour désactiver l’intégration avec le stockage Exchange 2013, désactivez la case à cocher **Intégration de Microsoft Exchange**.

5.  Cliquez sur **Valider**.

## Voir aussi

#### Concepts

[Fonctionnement de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md)  

#### Autres ressources

[Gestion des options de configuration de l’archivage dans Lync Server 2013 pour votre organisation, vos sites et vos pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)

