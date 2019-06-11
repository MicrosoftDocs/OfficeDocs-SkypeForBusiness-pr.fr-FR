---
title: 'Lync Server 2013: affecter une stratégie de mobilité par utilisateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user mobility policy
ms:assetid: d8bf997f-4bc7-48d3-973b-323505f55e9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721902(v=OCS.15)
ms:contentKeyID: 49733836
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e79a9b76ac4774bbbac7772bef19902d6d70f15a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846897"
---
# <a name="assign-a-per-user-mobility-policy-in-lync-server-2013"></a>Affecter une stratégie de mobilité par utilisateur dans Lync Server 2013

 


La stratégie de mobilité est l’un des paramètres individuels d’un compte d’utilisateur que vous pouvez configurer dans le panneau de configuration de Lync Server ou Lync Server Management Shell.

## <a name="to-assign-a-per-user-mobility-policy-with-lync-server-control-panel"></a>Pour attribuer une stratégie de mobilité par utilisateur avec le panneau de configuration de Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4.  Recherchez un utilisateur à l’aide de l’une des méthodes suivantes :
    
      - Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP (Session Initiation Protocol) ou de l’URI de ligne du compte d’utilisateur, puis cliquez sur **Rechercher**.
    
      - Si vous avez enregistré une requête, cliquez sur l’icône **Ouvrir une requête**, puis sur **Rechercher** dans la boîte de dialogue **Ouvrir** pour rechercher la requête (un fichier .usf).

5.  (Facultatif) Indiquez des critères de recherche supplémentaires pour affiner les résultats :
    
    1.  Cliquez sur **Ajouter un filtre**.
    
    2.  Entrez la propriété utilisateur en tapant son nom ou en cliquant sur la flèche de la liste déroulante.
    
    3.  Dans la liste déroulante **Égal à**, cliquez sur l’opérateur (par exemple, **Égal à** ou **Pas égal à**).
    
    4.  Selon la propriété utilisateur que vous avez sélectionnée, entrez le critère que vous souhaitez utiliser pour filtrer les résultats de recherche en le tapant ou en cliquant sur la flèche dans la liste déroulante.
        

        > [!TIP]  
        > Pour ajouter des clauses de recherche supplémentaires à la requête, cliquez sur <STRONG>Ajouter un filtre</STRONG>.

    
    5.  Cliquez sur **Rechercher**.

6.  Cliquez sur un utilisateur dans les résultats, puis sur **Action** et sur **Attribuer des stratégies**.
    

    > [!TIP]  
    > Si vous voulez appliquer la même stratégie de mobilité par utilisateur à plusieurs utilisateurs, sélectionnez plusieurs utilisateurs dans les résultats de la recherche, cliquez sur <STRONG>actions</STRONG>, puis sur <STRONG>affecter des stratégies</STRONG>.



7.  Dans **attribution de stratégies**de **mobilité**, effectuez l’une des opérations suivantes:
    

    > [!NOTE]  
    > Dans la mesure où il existe plusieurs stratégies que vous pouvez configurer dans <STRONG>affecter des stratégies</STRONG>, <STRONG> &lt;l’option rester&gt; en</STRONG> cours est activée par défaut pour chaque stratégie dans la boîte de dialogue. Continuez à utiliser la stratégie précédemment attribuée à l’utilisateur sans apporter de modification au paramètre.

    
      - Sélectionnez ** \<automatique\> ** pour permettre à Lync Server 2013 de choisir automatiquement la stratégie de niveau global ou, s’il est défini, la stratégie au niveau du site.
    
      - Cliquez sur le nom d’une stratégie de mobilité par utilisateur que vous avez précédemment définie dans la page **stratégie de mobilité** .
        

        > [!TIP]  
        > Pour vous aider à décider quelle stratégie attribuer, après avoir cliqué sur un nom de stratégie, cliquez sur <STRONG>Afficher</STRONG> pour afficher les droits et autorisations des utilisateurs définis dans la stratégie.



8.  Lorsque vous avez terminé, cliquez sur **OK**.

## <a name="assigning-a-per-user-mobility-policy-by-using-windows-powershell-cmdlets"></a>Attribution d’une stratégie de mobilité par utilisateur à l’aide des applets de cmdlet Windows PowerShell

Vous pouvez attribuer des stratégies de mobilité par utilisateur à l’aide de Windows PowerShell et de l’applet **de passe Grant-CsMobilityPolicy** . Vous pouvez exécuter cette applet de commande sur Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell».

## <a name="to-assign-a-per-user-mobility-policy-to-a-single-user"></a>Pour attribuer une stratégie de mobilité par utilisateur à un utilisateur unique

  - La commande suivante affecte le RedmondMobilityPolicy de stratégie de mobilité par utilisateur à l’utilisateur Ken Myer.
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName "RedmondMobilityPolicy"

## <a name="to-assign-a-per-user-mobility-policy-to-multiple-users"></a>Pour attribuer une stratégie de mobilité par utilisateur à plusieurs utilisateurs

  - La commande suivante affecte le RedmondMobilityPolicy de stratégie de mobilité par utilisateur à tous les utilisateurs actuellement affectés à la stratégie NorthAmericaMobilityPolicy. Pour plus d’informations sur le paramètre de filtre utilisé dans cette commande, voir [Get-Csuser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)).
    
        Get-CsUser -Filter {MobilityPolicy -eq "NorthAmericaMobilityPolicy"} | Grant-CsMobilityPolicy -PolicyName "RedmondMobilityPolicy"

## <a name="to-unassign-a-per-user-mobility-policy"></a>Pour annuler l’affectation d’une stratégie de mobilité par utilisateur

  - La commande suivante annule l’affectation d’une stratégie de mobilité par utilisateur précédemment affectée à Ken Myer. Une fois l’affectation de la stratégie par utilisateur annulée, Ken Myer sera automatiquement géré en utilisant la stratégie globale ou, le cas échéant, sa stratégie de site local. Une stratégie de site est prioritaire sur la stratégie globale.
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName $Null

Pour plus d’informations, consultez la rubrique [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/hh690038\(v=ocs.15\)).

## <a name="see-also"></a>Voir aussi


[Configuration de la stratégie de mobilité dans Lync Server 2013](lync-server-2013-configuring-mobility-policy.md)

