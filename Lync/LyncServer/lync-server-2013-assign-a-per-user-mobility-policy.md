---
title: 'Lync Server 2013 : affecter une stratégie de mobilité par utilisateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user mobility policy
ms:assetid: d8bf997f-4bc7-48d3-973b-323505f55e9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721902(v=OCS.15)
ms:contentKeyID: 49733836
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1014bce74e0e7dcd789c9b2948c029f4b40ecb9a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030137"
---
# <a name="assign-a-per-user-mobility-policy-in-lync-server-2013"></a>Attribuer une stratégie de mobilité par utilisateur dans Lync Server 2013

 


La stratégie de mobilité est l’un des paramètres individuels d’un compte d’utilisateur que vous pouvez configurer dans le panneau de configuration Lync Server ou Lync Server Management Shell.

## <a name="to-assign-a-per-user-mobility-policy-with-lync-server-control-panel"></a>Pour affecter une stratégie de mobilité par utilisateur avec le panneau de configuration Lync Server

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

6.  Cliquez sur un utilisateur dans les résultats, sur **Action**, puis sur **Attribuer des stratégies**.
    

    > [!TIP]  
    > Si vous voulez que la même stratégie de mobilité par utilisateur s’applique à plusieurs utilisateurs, sélectionnez-les dans les résultats de la recherche, cliquez sur <STRONG>Actions</STRONG>, puis sur <STRONG>Attribuer des stratégies</STRONG>.



7.  Dans **Attribuer des stratégies**, sous **Stratégie de mobilité**, effectuez l’une des actions suivantes :
    

    > [!NOTE]  
    > Étant donné qu’il existe plusieurs stratégies que vous pouvez configurer dans <STRONG>affecter des stratégies</STRONG>, <STRONG> &lt;garder en&gt; tant que est</STRONG> sélectionnée par défaut pour chaque stratégie dans la boîte de dialogue. Continuez à utiliser la stratégie précédemment attribuée à l’utilisateur sans apporter de modification au paramètre.

    
      - Sélectionnez ** \<automatique\> ** pour permettre à Lync Server 2013 de choisir automatiquement la stratégie au niveau global ou, si elle est définie, la stratégie au niveau du site.
    
      - Cliquez sur le nom d’une stratégie de mobilité par utilisateur que vous avez précédemment définie sur la page **Stratégie de mobilité**.
        

        > [!TIP]  
        > Pour vous aider à décider quelle stratégie attribuer, après avoir cliqué sur un nom de stratégie, cliquez sur <STRONG>Afficher</STRONG> pour afficher les droits et autorisations des utilisateurs définis dans la stratégie.



8.  Lorsque vous avez terminé, cliquez sur **OK**.

## <a name="assigning-a-per-user-mobility-policy-by-using-windows-powershell-cmdlets"></a>Affectation d’une stratégie de mobilité par utilisateur à l’aide des applets de commande Windows PowerShell

Vous pouvez affecter des stratégies de mobilité par utilisateur à l’aide de Windows PowerShell et de la cmdlet **Grant-CsMobilityPolicy** . Vous pouvez exécuter cette applet de commande à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.

## <a name="to-assign-a-per-user-mobility-policy-to-a-single-user"></a>Pour attribuer une stratégie de mobilité par utilisateur à un seul utilisateur

  - La commande suivante attribue la stratégie de mobilité par utilisateur RedmondMobilityPolicy à l’utilisateur Ken Myer.
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName "RedmondMobilityPolicy"

## <a name="to-assign-a-per-user-mobility-policy-to-multiple-users"></a>Pour attribuer une stratégie de mobilité par utilisateur à plusieurs utilisateurs

  - La commande suivante attribue la stratégie de mobilité par utilisateur RedmondMobilityPolicy à tous les utilisateurs auxquels la stratégie NorthAmericaMobilityPolicy est actuellement attribuée. Pour plus d’informations sur le paramètre Filter utilisé dans cette commande, reportez-vous à [Get-Csuser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)).
    
        Get-CsUser -Filter {MobilityPolicy -eq "NorthAmericaMobilityPolicy"} | Grant-CsMobilityPolicy -PolicyName "RedmondMobilityPolicy"

## <a name="to-unassign-a-per-user-mobility-policy"></a>Pour annuler l’attribution d’une stratégie de mobilité par utilisateur

  - La commande suivante annule l’attribution de toute stratégie de mobilité par utilisateur précédemment attribuée à Ken Myer. Une fois l’attribution de la stratégie par utilisateur annulée, Ken Myer sera automatiquement géré à l’aide de la stratégie globale ou, si elle existe, sa stratégie de site locale. Une stratégie de site est prioritaire sur la stratégie globale.
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName $Null

Pour plus d’informations, voir [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/hh690038\(v=ocs.15\)).

## <a name="see-also"></a>Voir aussi


[Configuration de la stratégie de mobilité dans Lync Server 2013](lync-server-2013-configuring-mobility-policy.md)

