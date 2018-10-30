---
title: Attribution d’une stratégie d’archivage par utilisateur
TOCTitle: Attribution d’une stratégie d’archivage par utilisateur
ms:assetid: a12ca483-b235-460f-b3fe-130fb3087264
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg182560(v=OCS.15)
ms:contentKeyID: 49298358
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Attribution d’une stratégie d’archivage par utilisateur

 

_**Dernière rubrique modifiée :** 2013-02-22_

La stratégie d’archivage est l’un des paramètres d’un compte d’utilisateur que vous pouvez configurer dans le Panneau de configuration Lync Server 2013.

Le déploiement d’une ou de plusieurs stratégies d’archivage par utilisateur est facultatif. Vous pouvez également déployer une stratégie d’archivage uniquement au niveau global ou au niveau d’un site. Si vous déployez des stratégies au niveau utilisateur, vous devez les attribuer de manière explicite aux objets User, Group ou Contact. Les conditions requises pour l’archivage sont automatiquement définies par défaut sur celles de la stratégie de conférence de niveau global si aucune stratégie par utilisateur ou au niveau d’un site spécifique n’est attribuée.

Après avoir créé au moins une stratégie d’archivage par utilisateur, utilisez les procédures de cette rubrique pour attribuer la stratégie qui précise de manière appropriée si les communications internes, les communications externes d’un utilisateur particulier ou les deux seront archivées par le serveur.

Pour plus d’informations sur la création de stratégies d’archivage par utilisateur, voir [Création d’une stratégie d’archivage pour activer ou désactiver l’archivage des communications internes ou externes pour des sites ou utilisateurs spécifiques](lync-server-2013-creating-an-archiving-policy-to-enable-or-disable-archiving-of-internal-or-external-communications-for-specific-sites-or-users.md).

## Pour attribuer une stratégie d’archivage par utilisateur

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4.  Recherchez un utilisateur à l’aide de l’une des méthodes suivantes :
    
      - Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP ou de l’URI de ligne du compte d’utilisateur, puis cliquez sur **Rechercher**.
    
      - Si vous avez enregistré une requête, cliquez sur l’icône **Ouvrir une requête**, puis sur **Rechercher** dans la boîte de dialogue **Ouvrir** pour localiser la requête (un fichier .usf).

5.  (Facultatif) Indiquez des critères de recherche supplémentaires pour affiner les résultats :
    
    1.  Cliquez sur **Ajouter un filtre**.
    
    2.  Entrez la propriété utilisateur en tapant son nom ou en cliquant sur la flèche dans la liste déroulante.
    
    3.  Dans la liste déroulante **Égal à**, cliquez sur l’opérateur (par exemple, **Égal à** ou **Pas égal à**).
    
    4.  Selon la propriété utilisateur que vous avez sélectionnée, entrez le critère que vous souhaitez utiliser pour filtrer les résultats de recherche en le tapant ou en cliquant sur la flèche dans la liste déroulante.
        
        > [!TIP]  
        > Pour ajouter des clauses de recherche supplémentaires à la requête, cliquez sur <strong>Ajouter un filtre</strong>.    
    5.  Cliquez sur **Rechercher**.

6.  Cliquez sur un utilisateur dans les résultats, puis sur **Action** et sur **Attribuer des stratégies**.
    
    > [!TIP]  
    > Si vous voulez que la même stratégie d’archivage par utilisateur s’applique à plusieurs utilisateurs, sélectionnez-les dans les résultats de la recherche, cliquez sur <strong>Actions</strong>, puis sur <strong>Attribuer des stratégies</strong>.

7.  Dans **Attribuer des stratégies**, sous **Stratégie d’archivage**, effectuez l’une des opérations suivantes :
    
    > [!NOTE]  
    > Comme vous pouvez configurer plusieurs stratégies à partir de la boîte de dialogue <strong>Attribuer des stratégies</strong>, l’option <strong>&lt;Conserver tel quel&gt;</strong> est sélectionnée par défaut pour chaque stratégie de la boîte de dialogue. Continuez à utiliser la stratégie précédemment attribuée à l’utilisateur sans apporter de modification au paramètre.    
      - Autorisez Lync Server 2013 à choisir automatiquement la stratégie au niveau global ou, si elle a été définie, la stratégie au niveau du site.
    
      - Cliquez sur le nom d’une stratégie d’archivage par utilisateur que vous avez précédemment définie dans la page **Stratégie d’archivage**.
        
        > [!TIP]  
        > Pour vous aider à décider de la stratégie à attribuer, après avoir cliqué sur le nom d’une stratégie, cliquez sur <strong>Afficher</strong> pour afficher les droits et les autorisations associés à la stratégie.

8.  Lorsque vous avez terminé, cliquez sur **OK**.

## Assignation d’une stratégie d’archivage par utilisateur à l’aide d’applets de commande Windows PowerShell

Les stratégies d’archivage par utilisateur peuvent également être assignées à l’aide de Windows PowerShell et de l’applet de commande **Grant-CsArchivingPolicy**. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Assignation d’une stratégie d’archivage par utilisateur à un utilisateur unique

  - La commande suivante assigne la stratégie d’archivage par utilisateur RedmondArchivingPolicy à l’utilisateur Ken Myer.
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

## Assignation d’une stratégie d’archivage par utilisateur à plusieurs utilisateurs

  - Cette commande assigne la stratégie d’archivage par utilisateur RedmondArchivingPolicy à tous les utilisateurs qui ont un compte hébergé sur le pool de serveurs d’inscriptions atl-cs-001.litwareinc.com. Pour plus d’informations sur le paramètre Filter utilisé dans cette commande, voir la documentation de l’applet de commande [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser).
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

## Annulation de l’assignation d’une stratégie d’archivage par utilisateur

  - La commande suivante annule l’assignation d’une stratégie d’archivage par utilisateur précédemment affectée à Ken Myer. Lorsque cette stratégie par utilisateur n’est plus assignée à Ken Myer, celui-ci est géré automatiquement par la stratégie globale ou, le cas échéant, par la stratégie de site locale associée. La stratégie de site est prioritaire sur la stratégie globale.
    
        Grant-CsarchivingPolicy -Identity "Ken Myer" -PolicyName $Null

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Grant-CsArchivingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsArchivingPolicy).

## Voir aussi

#### Tâches

[Création d’une stratégie d’archivage pour activer ou désactiver l’archivage des communications internes ou externes pour des sites ou utilisateurs spécifiques](lync-server-2013-creating-an-archiving-policy-to-enable-or-disable-archiving-of-internal-or-external-communications-for-specific-sites-or-users.md)  

#### Autres ressources

[Attribution de stratégies par utilisateur dans Lync Server 2013](lync-server-2013-assigning-per-user-policies.md)

