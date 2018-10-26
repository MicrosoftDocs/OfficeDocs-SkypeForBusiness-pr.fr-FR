---
title: "Act. ou dés. de l’archivage de sessions de mes. instantanée ou de conférence"
TOCtitle: "Act. ou dés. de l’archivage de sessions de mes. instantanée ou de conférence"
ms:assetid: aa4b5983-dbe1-4d64-8a18-fe2c33994e94
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg182567(v=OCS.15)
ms:contentKeyID: 49298469
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Activation ou désactivation de l’archivage de sessions de messagerie instantanée ou de conférence

 

_**Dernière rubrique modifiée :** 2012-10-10_

Dans le Panneau de configuration Lync Server 2013, vous utilisez des configurations d’archivage pour activer et désactiver l’archivage des session de messagerie instantanée, de conférence, ou les deux. Les configurations de l’archivage sont les suivantes :

  - Configuration globale créée par défaut lorsque vous déployez Lync Server 2013.

  - Configurations facultatives au niveau du site et au niveau du pool que vous pouvez créer et utiliser pour spécifier la manière de mettre en œuvre l’archivage de sites ou pools spécifiques.

Vous commencez par définir les configurations de l’archivage lorsque vous déployez l’archivage, mais vous pouvez modifier, ajouter et supprimer des configurations à l’issue du déploiement. Pour plus d’informations sur la manière de mettre en œuvre les configurations de l’archivage, notamment sur les options que vous pouvez spécifier et la hiérarchie des configurations de l’archivage, voir [Fonctionnement de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, dans la documentation de déploiement ou dans la documentation des opérations.

> [!NOTE]  
> Pour utiliser l’archivage, vous devez configurer des stratégies d’archivage afin de spécifier si l’archivage doit être activé pour les communications internes, pour les communications externes, ou pour les deux pour les utilisateurs hébergés sur Lync Server 2013. Par défaut, l’archivage n’est pas activé pour les communications internes ou externes. Avant d’activer l’archivage dans des stratégies, vous devez spécifier les configurations d’archivage appropriées pour votre déploiement et, éventuellement, pour des sites et pools spécifiques, comme décrit dans cette section. Pour plus d’informations sur l’activation de l’archivage, voir <a href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuration et affectation des stratégies d’archivage</a> dans la documentation de déploiement.<br />
Si, après avoir déployé l’archivage, vous décidez d’utiliser l’intégration de Microsoft Exchange pour stocker des données et fichiers d’archivage sur des serveurs Exchange 2013 et que tous vos utilisateurs sont hébergés sur vos serveurs Exchange 2013, il est préférable de supprimer la configuration de la base de données SQL Server de votre topologie. Vous devez pour cela utiliser le Générateur de topologie. Pour plus d’informations, voir <a href="lync-server-2013-changing-archiving-database-options.md">Modification des options de la base de données d’archivage dans Lync Server 2013</a> dans la documentation des opérations.

## Pour activer ou désactiver l’archivage des sessions de messagerie instantanée ou de conférence

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Configuration d’archivage**.

4.  Sélectionnez la configuration de pool, de site ou globale appropriée dans la liste des configurations d’archivage, cliquez sur **Modifier**, sur **Afficher les détails**, puis procédez comme suit :
    
      - Pour activer l’archivage uniquement pour les sessions de messagerie instantanée, cliquez sur **Archiver les sessions de messagerie instantanée**.
    
      - Pour activer l’archivage à la fois pour les sessions de messagerie instantanée et les conférences, cliquez sur **Archiver les sessions de messagerie instantanée et de conférence web**.
    
      - Pour désactiver l’archivage pour une stratégie, cliquez sur **Désactiver l’archivage**.

5.  Cliquez sur **Valider**.

## Voir aussi

#### Autres ressources

[Gestion des options de configuration de l’archivage dans Lync Server 2013 pour votre organisation, vos sites et vos pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
[Configuration et affectation des stratégies d’archivage](lync-server-2013-configuring-and-assigning-archiving-policies.md)

