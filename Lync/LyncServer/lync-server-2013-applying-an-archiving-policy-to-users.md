---
title: Application d’une stratégie d’archivage à des utilisateurs
TOCTitle: Application d’une stratégie d’archivage à des utilisateurs
ms:assetid: 624a7d3e-389d-403a-97e5-f7bb17023ef3
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg521004(v=OCS.15)
ms:contentKeyID: 49297400
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Application d’une stratégie d’archivage à des utilisateurs

 

_**Dernière rubrique modifiée :** 2013-02-23_

Si un utilisateur a été activé pour Lync Server 2013 et que vous avez créé une ou plusieurs stratégies utilisateur pour archiver les utilisateurs hébergés sur Lync Server 2013, vous pouvez implémenter la prise en charge de l’archivage pour des utilisateurs spécifiques en appliquant les stratégies appropriées à ces utilisateurs ou groupes d’utilisateurs. Par exemple, si vous créez une stratégie permettant de prendre en charge l’archivage des communications internes, vous pouvez l’appliquer à au moins un utilisateur ou groupe d’utilisateurs de façon à permettre la prise en charge des communications Lync Server 2013 de l’utilisateur.

> [!NOTE]  
> Si vous avez activé l’intégration de Microsoft Exchange pour votre déploiement, les stratégies d’archive permanente d’Exchange déterminent si l’archivage est activé pour les utilisateurs qui sont hébergés sur Exchange 2013 et dont les boîtes aux lettres sont archivées de manière permanente. Pour plus d’informations, voir <a href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Configuration des stratégies pour l’archivage lors de l’utilisation de l’intégration Exchange Server</a> dans la documentation du déploiement.<br />
Vous devez définir toutes les options appropriées dans les configurations de l’archivage avant d’activer l’archivage. Pour plus d’informations, voir <a href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Gestion des options de configuration de l’archivage dans Lync Server 2013 pour votre organisation, vos sites et vos pools</a> dans la documentation des opérations.

Suivez la procédure décrite dans cette rubrique pour appliquer une stratégie utilisateur d’archivage précédemment créée à un ou plusieurs comptes d’utilisateur ou groupes d’utilisateurs.

## Pour appliquer une stratégie utilisateur d’archivage à un compte d’utilisateur

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur à configurer.

4.  Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.

5.  Dans **Modifier l’utilisateur Lync Server**, sous **Stratégie d’archivage**, sélectionnez la stratégie utilisateur d’archivage à appliquer.
    
    > [!NOTE]  
    > Les paramètres <strong>&lt;Automatique&gt;</strong> appliquent les paramètres d’installation du serveur par défaut. Ces paramètres sont appliqués automatiquement par le serveur.

6.  Cliquez sur **Valider**.

## Affectation d’une stratégie d’archivage par utilisateur à l’aide des applets de commande Lync Server Management Shell

Il est aussi possible d’affecter des stratégies d’archivage par utilisateur à l’aide de Lync ServerWindows PowerShell et de l’applet de commande **Grant-CsArchivingPolicy**. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Affectation d’une stratégie d’archivage par utilisateur à un utilisateur unique

  - La commande suivante affecte la stratégie d’archivage par utilisateur RedmondArchivingPolicy à l’utilisateur Ken Myer.
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

## Affectation d’une stratégie d’archivage par utilisateur à plusieurs utilisateurs

  - Cette commande affecte la stratégie d’archivage par utilisateur RedmondArchivingPolicy à tous les utilisateurs dont les comptes sont hébergés sur le pool de serveurs d’inscriptions atl-cs-001.litwareinc.com. Pour plus d’informations sur le paramètre Filter utilisé dans cette commande, voir la documentation sur l’applet de commande [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser).
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

## Annulation de l’affectation d’une stratégie d’archivage par utilisateur

  - La commande suivante annule l’affectation d’une stratégie d’archivage par utilisateur précédemment affectée à Ken Myer. Lorsque cette stratégie par utilisateur n’est plus affectée à Ken Myer, celui-ci est automatiquement géré par la stratégie globale ou, le cas échéant, par la stratégie de site locale associée. La stratégie de site est prioritaire sur la stratégie globale.
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

Pour plus d’informations, voir la documentation sur l’applet de commande [Grant-CsArchivingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsArchivingPolicy).

## Voir aussi

#### Autres ressources

[Gestion de l'archivage des communications internes et externes dans Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
[Attribution de stratégies par utilisateur dans Lync Server 2013](lync-server-2013-assigning-per-user-policies.md)

