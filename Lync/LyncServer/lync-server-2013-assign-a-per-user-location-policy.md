---
title: Affectation d’une stratégie d’emplacement par utilisateur
TOCTitle: Affectation d’une stratégie d’emplacement par utilisateur
ms:assetid: 343f2de3-a0ae-4403-8456-6e520b579d32
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg520974(v=OCS.15)
ms:contentKeyID: 49296824
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Affectation d’une stratégie d’emplacement par utilisateur

 

_**Dernière rubrique modifiée :** 2013-02-22_

La stratégie d’emplacement est un des paramètres de compte d’utilisateur individuels que vous pouvez configurer dans le Panneau de configuration Lync Server.

Le déploiement d’une ou de plusieurs stratégies d’emplacement est facultatif. Vous pouvez aussi déployer uniquement une stratégie d’emplacement au niveau global ou au niveau du sous-réseau. Si vous déployez des stratégies au niveau utilisateur, vous devez les attribuer de manière explicite aux objets User, Group ou Contact. Les paramètres Enhanced 9-1-1 (E9-1-1) sont automatiquement définis dans la stratégie de niveau global lorsqu’aucune stratégie n’est affectée au niveau du sous-réseau ou de l’utilisateur.

Une fois que vous avez créé au moins une stratégie d’emplacement au niveau utilisateur, vous devez affecter la stratégie qui stipule les paramètres devant être appliqués par le serveur aux appels d’urgence passés par un utilisateur donné. Pour cela, procédez comme suit.

Pour obtenir la liste des paramètres de stratégie d’emplacement disponibles, voir [Définition de la stratégie d’emplacement pour Lync Server 2013](lync-server-2013-defining-the-location-policy.md).

Pour plus d’informations sur la création de stratégies d’emplacement, voir [Créer des stratégies d’emplacement dans Lync Server 2013](lync-server-2013-create-location-policies.md).

## Pour affecter une stratégie d’emplacement au niveau utilisateur

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
    > Si vous voulez appliquer la même stratégie d’emplacement de niveau utilisateur à plusieurs utilisateurs, sélectionnez plusieurs utilisateurs dans les résultats, puis cliquez sur <strong>Actions</strong> et sur <strong>Attribuer des stratégies</strong>.

7.  Dans **Attribuer des stratégies**, sous **Stratégie d’emplacement**, effectuez l’une des actions suivantes :
    
    > [!NOTE]  
    > Comme vous pouvez configurer plusieurs stratégies à partir de la boîte de dialogue <strong>Attribuer des stratégies</strong>, l’option <strong>&lt;Conserver tel quel&gt;</strong> est sélectionnée par défaut pour chaque stratégie de la boîte de dialogue. Continuez à utiliser la stratégie précédemment attribuée à l’utilisateur sans apporter de modification au paramètre.    
      - Autorisez Lync Server 2013 à choisir automatiquement la stratégie de niveau global ou, si elle est définie, la stratégie de niveau sous-réseau.
    
      - Cliquez sur le nom d’une stratégie d’emplacement de niveau utilisateur que vous avez définie en exécutant l’applet de commande **New-CsLocationPolicy**.
        
        > [!TIP]  
        > Pour vous aider à décider de la stratégie à attribuer, après avoir cliqué sur le nom d’une stratégie, cliquez sur <strong>Afficher</strong> pour afficher les droits et les autorisations associés à la stratégie.

8.  Lorsque vous avez terminé, cliquez sur **OK**.

## Pour affecter une stratégie d’emplacement utilisateur à l’aide de Lync Server Management Shell

Vous pouvez affecter des stratégies d’emplacement utilisateur à l’aide de l’applet de commande Grant-CsLocationPolicy. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Pour affecter une stratégie d’emplacement utilisateur à un utilisateur unique

  - La commande suivante affecte la stratégie d’emplacement utilisateur RedmondLocationPolicy à l’utilisateur Ken Myer.
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName "RedmondLocationPolicy"

## Pour affecter une stratégie d’emplacement utilisateur à plusieurs utilisateurs

  - Cette commande affecte la stratégie d’emplacement utilisateur AccountingDepartmentLocationPolicy à tous les utilisateurs qui travaillent au service comptabilité. Pour plus d’informations sur le paramètre LdapFilter utilisé dans cette commande, voir la documentation de l’applet de commande [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser).
    
        Get-CsUser -LdapFilter "Department=Accounting" | Grant-CsLocationPolicy -PolicyName "AccountingDepartmentLocationPolicy"

## Pour supprimer l’affectation d’une stratégie d’emplacement utilisateur

  - La commande suivante supprime l’affectation d’une stratégie d’emplacement utilisateur précédemment affectée à Ken Myer. Lorsque cette stratégie utilisateur n’est plus affectée à Ken Myer, celui-ci est automatiquement géré par la stratégie globale ou, le cas échéant, par la stratégie de site locale associée. La stratégie de site est prioritaire sur la stratégie globale.
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName $Null

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Grant-CsLocationPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsLocationPolicy).

