---
title: Activation ou désactivation de la purge des données archivées
TOCTitle: Activation ou désactivation de la purge des données archivées
ms:assetid: 28cef09f-0970-4fc3-8315-f26689e3e187
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg520968(v=OCS.15)
ms:contentKeyID: 49296681
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Activation ou désactivation de la purge des données archivées

 

_**Dernière rubrique modifiée :** 2013-02-23_

Dans le Panneau de configuration Lync Server 2013, vous utilisez les configurations d’archivage pour activer et désactiver le vidage et configurer son mode d’implémentation. Les configurations d’archivage sont les suivantes :

  - une configuration globale créée par défaut lorsque vous déployez Lync Server 2013 ;

  - des configurations facultatives au niveau du site et du pool que vous pouvez créer et utiliser pour spécifier le mode d’implémentation de l’archivage de sites ou pools spécifiques.

Vous définissez les configurations d’archivage lorsque vous déployez l’archivage, mais vous pouvez modifier, ajouter et supprimer des configurations une fois le déploiement terminé. Pour plus d’informations sur l’implémentation des configurations d’archivage, notamment les options que vous pouvez spécifier et la hiérarchie des configurations d’archivage, voir [Fonctionnement de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md) dans la documentation de planification, la documentation de déploiement ou la documentation des opérations.

> [!NOTE]  
> Pour utiliser l’archivage des utilisateurs hébergés sur Lync Server 2013, vous devez configurer des stratégies d’archivage afin de spécifier si l’archivage doit être activé pour les communications internes, les communications externes, ou les deux. Par défaut, l’archivage n’est pas activé pour les communications internes ou externes. Avant d’activer l’archivage dans des stratégies, vous devez spécifier les configurations d’archivage appropriées pour votre déploiement et, éventuellement, pour des sites et pools spécifiques, comme décrit dans cette section. Pour plus d’informations sur l’activation de l’archivage, voir <a href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configuration et affectation des stratégies d’archivage</a> dans la documentation de déploiement.<br />
Si, après avoir déployé l’archivage, vous décidez d’utiliser l’intégration de Microsoft Exchange pour stocker des données et fichiers d’archivage sur des serveurs Exchange 2013 et que tous vos utilisateurs sont hébergés sur vos serveurs Exchange 2013, il est préférable de supprimer la configuration de la base de données SQL Server de votre topologie. Vous devez utiliser le Générateur de topologie pour ce faire. Pour plus d’informations, voir <a href="lync-server-2013-changing-archiving-database-options.md">Modification des options de la base de données d’archivage dans Lync Server 2013</a> dans la documentation des opérations.

## Pour activer ou désactiver le vidage de l’archivage

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Configuration d’archivage**.

4.  Cliquez sur le nom de la configuration appropriée (globale, du site ou du pool) dans la liste des configurations d’archivage, cliquez sur **Modifier**, sur **Afficher les détails**, puis procédez comme suit :
    
      - Pour activer le vidage, activez la case à cocher **Activer le vidage des données d’archivage** et effectuez l’une des actions suivantes :
        
          - Pour vider tous les enregistrements, cliquez sur **Vider les données d’archivage exportées et enregistrées après un délai maximal (jours)**, puis indiquez le nombre de jours.
        
          - Pour ne purger que les données qui ont été exportées, cliquez sur **Vider uniquement les données d’archivage exportées**.
    
      - Pour désactiver le vidage, désactivez la case à cocher **Activer le vidage des données d’archivage**.

5.  Cliquez sur **Valider**.

## Activation et désactivation du vidage des données d’archivage à l’aide des applets de commande Lync Server Management Shell

L’activation et la désactivation du vidage automatique des données d’archivage peuvent aussi être gérées à l’aide de Windows PowerShell et de l’applet de commande **Set-CsArchivingConfiguration**. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Activation du vidage de toutes les données d’archivage

  - Pour activer le vidage de toutes les données d’archivage, définissez la propriété **EnablePurging** sur true ($True). Par exemple :
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
    
    Une fois cette commande exécutée, Lync Server videra tous les jours tous les enregistrements d’archivage antérieurs à la valeur spécifiée pour la propriété **KeepArchivingDataForDays**.

## Activation du vidage exclusif des données d’archivage exportées

  - Pour limiter le vidage aux enregistrements d’archivage qui ont été exportés dans un fichier de données (à l’aide de l’applet de commande [Export-CsArchivingData](https://docs.microsoft.com/en-us/powershell/module/skype/Export-CsArchivingData)) vous devez aussi définir la propriété PurgeExportedArchivesOnly sur True ($True). Par exemple :
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
    
    Une fois cette commande exécutée, Lync Server ne videra que les enregistrements d’archivage qui répondent à deux critères : 1) ils sont antérieurs à la valeur spécifiée pour la propriété **KeepArchivingDataForDays** et 2) ils ont été exportés à l’aide de l’applet de commande **Export-CsArchivingData**.

## Désactivation du vidage de toutes les données d’archivage

  - Pour désactiver le vidage automatique des enregistrements d’archivage, définissez la propriété **EnablePurging** sur False ($False). Par exemple :
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False

Pour plus d’informations, notamment des options supplémentaires pour le vidage des données d’archivage, voir la rubrique d’aide de l’applet de commande [Set-CsArchivingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsArchivingConfiguration).

## Voir aussi

#### Concepts

[Fonctionnement de l’archivage dans Lync Server 2013](lync-server-2013-how-archiving-works.md)  

#### Autres ressources

[Configuration et affectation des stratégies d’archivage](lync-server-2013-configuring-and-assigning-archiving-policies.md)  
[Gestion des options de configuration de l’archivage dans Lync Server 2013 pour votre organisation, vos sites et vos pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)

