---
title: "Act/dés mode crit. pr bloq./aut. sess. mess. inst. et conf. web si échec arch."
TOCtitle: "Act/dés mode crit. pr bloq./aut. sess. mess. inst. et conf. web si échec arch."
ms:assetid: fafdcd2e-b778-4ed5-a25f-09208aa3b699
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg182609(v=OCS.15)
ms:contentKeyID: 49299417
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Activation ou désactivation du mode critique pour bloquer ou autoriser des sessions de messagerie instantanée et de conférences web en cas d’échec de l’archivage

 

_**Dernière rubrique modifiée :** 2013-02-23_

Dans le Panneau de configuration Lync Server 2013, utilisez les configurations d’archivage pour activer et désactiver le mode critique. Ceci s’applique aux conversations suivantes :

  - Une configuration globale crée par défaut lorsque vous déployez Lync Server 2013.

  - Des configurations facultatives au niveau du site et du pool que vous pouvez créer et utiliser pour spécifier la méthode d’implémentation de l’archivage pour les sites ou les pools spécifiques.

Nous vous conseillons de configurez d’abord les configurations d’archivage avant de déployer l’archivage, mais vous pouvez modifier, ajouter et supprimer des configurations après le déploiement. Pour plus d’informations sur l’implémentation des configurations d’archivage, notamment sur les options que vous pouvez spécifier et la hiérarchie des configurations d’archivage, voir [Fonctionnement de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation relative à la planification, au déploiement ou aux opérations.

> [!NOTE]  
> Pour utiliser l’archivage, vous devez configurer les stratégies d’archivage pour spécifier si l’archivage doit être activé pour les communications internes, externes, ou les deux, pour les utilisateurs hébergés sur Lync Server 2013. Par défaut, l’archivage n’est pas activé pour les communications internes ou externes. Avant d’activer l’archivage dans une stratégie, vous devez spécifier les configurations d’archivage adéquates pour votre déploiement et, éventuellement, pour des sites et des pools spécifiques, comme cela est décrit dans cette section. Pour plus d’informations sur l’activation de l’archivage, voir <a href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuration et affectation des stratégies d’archivage</a> dans la documentation de déploiement.<br />
Si, après le déploiement de l’archivage, vous décidez d’utiliser l’intégration Exchange Server pour stocker les données et les fichiers d’archivage sur les serveurs Exchange 2013 et que tous vos utilisateurs sont hébergés sur vos serveurs Exchange 2013, vous devez supprimer la configuration de base de données SQL Server de votre topologie. Vous devez utiliser Générateur de topologie pour cela. Pour plus d’informations, voir <a href="lync-server-2013-changing-archiving-database-options.md">Modification des options de la base de données d’archivage dans Lync Server 2013</a> dans la documentation des opérations.

## Pour activer ou désactiver le blocage des sessions de messagerie instantanée et de conférence Web en cas d’échec de l’archivage

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Configuration d’archivage**.

4.  Cliquez sur le nom de la configuration de site, de pool ou globale appropriée dans la liste des configurations d’archivage, puis sur **Modifier**, sur **Afficher les détails** et procédez comme suit : .

5.  Pour définir le comportement de l’archivage en cas d’échec, cochez ou décochez la case **Bloquer les sessions de messagerie instantanée ou de conférence Web en cas d’échec de l’archivage**.

6.  Cliquez sur **Valider**.

## Activation et désactivation du mode critique en utilisant les cmdlets Lync ServerWindows PowerShell

Vous pouvez activer ou désactiver le mode critique en utilisant la cmdlet **Set-CsArchivingConfiguration**. Vous pouvez exécuter cette cmdlet depuis l’un des environnement de ligne de commande Lync Server 2013 Management Shell ou depuis une session distante de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Activation du mode critique

  - Pour activer le mode critique, définissez la valeur de la propriété BlockOnArchiveFailure sur True ($True). Par exemple :
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True

## Désactivation du mode critique

  - Pour désactiver le mode critique, définissez la valeur de la propriété BlockOnArchiveFailure sur False ($False). Par exemple :
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False

Pour plus d’informations, recherchez la cmdlet [Set-CsArchivingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsArchivingConfiguration) dans la rubrique d’aide.

## Voir aussi

#### Tâches

[Modification des options de la base de données d’archivage dans Lync Server 2013](lync-server-2013-changing-archiving-database-options.md)  

#### Concepts

[Fonctionnement de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md)  

#### Autres ressources

[Gestion des options de configuration de l’archivage dans Lync Server 2013 pour votre organisation, vos sites et vos pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)

