---
title: Attribution d’une stratégie de mobilité par utilisateur
TOCTitle: Attribution d’une stratégie de mobilité par utilisateur
ms:assetid: d8bf997f-4bc7-48d3-973b-323505f55e9d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721902(v=OCS.15)
ms:contentKeyID: 49891566
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Attribution d’une stratégie de mobilité par utilisateur

 

_**Dernière rubrique modifiée :** 2013-02-22_

La stratégie de mobilité est l’un des paramètres individuels d’un compte utilisateur que vous pouvez configurer dans le Panneau de configuration Lync Server ou Lync Server Management Shell.

## Pour attribuer une stratégie de mobilité par utilisateur dans le Panneau de configuration Lync Server

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

6.  Cliquez sur un utilisateur dans les résultats, sur **Action**, puis sur **Attribuer des stratégies**.
    
    > [!TIP]  
    > Si vous voulez que la même stratégie de mobilité par utilisateur s’applique à plusieurs utilisateurs, sélectionnez-les dans les résultats de la recherche, cliquez sur <strong>Actions</strong>, puis sur <strong>Attribuer des stratégies</strong>.

7.  Dans **Attribuer des stratégies**, sous **Stratégie de mobilité**, effectuez l’une des actions suivantes :
    
    > [!NOTE]  
    > Du fait qu’il existe plusieurs stratégies configurables dans la boîte de dialogue <strong>Attribuer des stratégies</strong>, l’option <strong>&lt;Conserver tel quel&gt;</strong> est activée par défaut pour chaque stratégie dans la boîte de dialogue. Continuez à utiliser la stratégie précédemment attribuée à l’utilisateur sans apporter de modification au paramètre.    
      - Sélectionnez **\<Automatique\>** pour permettre à Lync Server 2013 de choisir automatiquement la stratégie au niveau global, ou, si elle est définie, la stratégie au niveau du site.
    
      - Cliquez sur le nom d’une stratégie de mobilité par utilisateur que vous avez précédemment définie sur la page **Stratégie de mobilité**.
        
        > [!TIP]  
        > Pour vous aider à décider quelle stratégie attribuer, après avoir cliqué sur un nom de stratégie, cliquez sur <strong>Afficher</strong> pour afficher les droits et autorisations des utilisateurs définis dans la stratégie.

8.  Lorsque vous avez terminé, cliquez sur **OK**.

## Attribution d’une stratégie de mobilité par utilisateur à l’aide des applets de commande Lync Server Management Shell

Vous pouvez attribuer les stratégies de mobilité par utilisateur en utilisant Lync Server Management Shell et l’applet de commande **Grant-CsMobilityPolicy**. Vous pouvez exécuter cette applet de commande à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Pour attribuer une stratégie de mobilité par utilisateur à un seul utilisateur

  - La commande suivante attribue la stratégie de mobilité par utilisateur RedmondMobilityPolicy à l’utilisateur Ken Myer.
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName "RedmondMobilityPolicy"

## Pour attribuer une stratégie de mobilité par utilisateur à plusieurs utilisateurs

  - La commande suivante attribue la stratégie de mobilité par utilisateur RedmondMobilityPolicy à tous les utilisateurs auxquels la stratégie NorthAmericaMobilityPolicy est actuellement attribuée. Pour plus d’informations sur le paramètre Filter utilisé dans cette commande, voir [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser).
    
        Get-CsUser -Filter {MobilityPolicy -eq "NorthAmericaMobilityPolicy"} | Grant-CsMobilityPolicy -PolicyName "RedmondMobilityPolicy"

## Pour annuler l’attribution d’une stratégie de mobilité par utilisateur

  - La commande suivante annule l’attribution de toute stratégie de mobilité par utilisateur précédemment attribuée à Ken Myer. Une fois l’attribution de la stratégie par utilisateur annulée, Ken Myer sera automatiquement géré à l’aide de la stratégie globale ou, si elle existe, sa stratégie de site locale. Une stratégie de site est prioritaire sur la stratégie globale.
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName $Null

Pour plus d’informations, voir [Grant-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsMobilityPolicy).

## Voir aussi

#### Tâches

[Configuration de la stratégie de mobilité dans Lync Server 2013](lync-server-2013-configuring-mobility-policy.md)

