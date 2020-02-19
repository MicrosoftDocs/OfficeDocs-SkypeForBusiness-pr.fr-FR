---
title: 'Lync Server 2013 : affecter une stratégie d’emplacement par utilisateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user location policy
ms:assetid: 343f2de3-a0ae-4403-8456-6e520b579d32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520974(v=OCS.15)
ms:contentKeyID: 48183794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d66df7f2d0c8a2b8603f7c08312f5b8b6aaad56
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134430"
---
# <a name="assign-a-per-user-location-policy-in-lync-server-2013"></a>Affecter une stratégie d’emplacement par utilisateur dans Lync Server 2013

 


La stratégie d’emplacement est l’un des paramètres individuels d’un compte d’utilisateur que vous pouvez configurer dans le panneau de configuration Lync Server.

Le déploiement d’une ou de plusieurs stratégies d’emplacement est facultatif. Vous pouvez aussi déployer uniquement une stratégie d’emplacement au niveau global ou au niveau du sous-réseau. Si vous déployez des stratégies au niveau utilisateur, vous devez les attribuer de manière explicite aux objets User, Group ou Contact. Les paramètres Enhanced 9-1-1 (E9-1-1) sont automatiquement définis dans la stratégie de niveau global lorsqu’aucune stratégie n’est affectée au niveau du sous-réseau ou de l’utilisateur.

Une fois que vous avez créé au moins une stratégie d’emplacement au niveau utilisateur, vous devez affecter la stratégie qui stipule les paramètres devant être appliqués par le serveur aux appels d’urgence passés par un utilisateur donné. Pour cela, procédez comme suit.

Pour obtenir la liste de tous les paramètres de stratégie d’emplacement disponibles, voir [définition de la stratégie d’emplacement pour Lync Server 2013](lync-server-2013-defining-the-location-policy.md).

Pour plus d’informations sur la création de stratégies d’emplacement, voir [Create location Policies in Lync Server 2013](lync-server-2013-create-location-policies.md).

## <a name="to-assign-a-per-user-location-policy-with-the-lync-server-control-panel"></a>Pour attribuer une stratégie d’emplacement par utilisateur à l’aide du panneau de configuration Lync Server

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

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
        > Pour ajouter des clauses de recherche supplémentaires à la requête, cliquez sur <STRONG>Ajouter un filtre</STRONG>.

    
    5.  Cliquez sur **Rechercher**.

6.  Cliquez sur un utilisateur dans les résultats, puis sur **Action** et sur **Attribuer des stratégies**.
    

    > [!TIP]  
    > Si vous voulez appliquer la même stratégie d’emplacement de niveau utilisateur à plusieurs utilisateurs, sélectionnez plusieurs utilisateurs dans les résultats, puis cliquez sur <STRONG>Actions</STRONG> et sur <STRONG>Attribuer des stratégies</STRONG>.



7.  Dans **Attribuer des stratégies**, sous **Stratégie d’emplacement**, effectuez l’une des actions suivantes :
    

    > [!NOTE]  
    > Étant donné qu’il existe plusieurs stratégies que vous pouvez configurer à l’aide de la boîte de dialogue <STRONG>affecter les stratégies</STRONG> , <STRONG> &lt;l’option conserver en tant que est&gt; </STRONG> sélectionnée par défaut pour chaque stratégie dans la boîte de dialogue. Continuez à utiliser la stratégie précédemment attribuée à l’utilisateur sans apporter de modification au paramètre.

    
      - Autoriser Lync Server 2013 à choisir automatiquement la stratégie au niveau global ou, si elle est définie, la stratégie au niveau du sous-réseau.
    
      - Cliquez sur le nom d’une stratégie d’emplacement de niveau utilisateur que vous avez définie en exécutant l’applet de commande **New-CsLocationPolicy**.
        

        > [!TIP]  
        > Pour vous aider à décider de la stratégie à attribuer, après avoir cliqué sur le nom d’une stratégie, cliquez sur <STRONG>Afficher</STRONG> pour afficher les droits et les autorisations associés à la stratégie.



8.  Lorsque vous avez terminé, cliquez sur **OK**.

## <a name="assigning-a-per-user-location-policy-by-using-lync-server-management-shell-cmdlets"></a>Affectation d’une stratégie d’emplacement par utilisateur à l’aide des applets de commande Lync Server Management Shell

Vous pouvez affecter des stratégies d’emplacement par utilisateur à l’aide de la cmdlet Grant-CsLocationPolicy. Vous pouvez exécuter cette cmdlet à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.

## <a name="to-assign-a-per-user-location-policy-to-a-single-user"></a>Pour affecter une stratégie d’emplacement utilisateur à un utilisateur unique

  - La commande suivante affecte la stratégie d’emplacement utilisateur RedmondLocationPolicy à l’utilisateur Ken Myer.
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName "RedmondLocationPolicy"

## <a name="to-assign-a-per-user-location-policy-to-multiple-users"></a>Pour affecter une stratégie d’emplacement utilisateur à plusieurs utilisateurs

  - Cette commande affecte la stratégie d’emplacement utilisateur AccountingDepartmentLocationPolicy à tous les utilisateurs qui travaillent au service comptabilité. Pour plus d’informations sur le paramètre LdapFilter utilisé dans cette commande, reportez-vous à la documentation de la cmdlet [Get-Csuser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -LdapFilter "Department=Accounting" | Grant-CsLocationPolicy -PolicyName "AccountingDepartmentLocationPolicy"

## <a name="to-unassign-a-per-user-location-policy"></a>Pour supprimer l’affectation d’une stratégie d’emplacement utilisateur

  - La commande suivante supprime l’affectation d’une stratégie d’emplacement utilisateur précédemment affectée à Ken Myer. Lorsque cette stratégie utilisateur n’est plus affectée à Ken Myer, celui-ci est automatiquement géré par la stratégie globale ou, le cas échéant, par la stratégie de site locale associée. La stratégie de site est prioritaire sur la stratégie globale.
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName $Null

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Grant-CsLocationPolicy](https://technet.microsoft.com/library/gg413049\(v=ocs.15\)) .

