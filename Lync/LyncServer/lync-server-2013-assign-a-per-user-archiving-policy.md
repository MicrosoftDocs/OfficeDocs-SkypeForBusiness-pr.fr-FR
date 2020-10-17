---
title: 'Lync Server 2013 : affecter une stratégie d’archivage par utilisateur'
description: 'Lync Server 2013 : affectez une stratégie d’archivage par utilisateur.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user archiving policy
ms:assetid: a12ca483-b235-460f-b3fe-130fb3087264
ms:mtpsurl: https://technet.microsoft.com/library/Gg182560(v=OCS.15)
ms:contentKeyID: 48185014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c81d7e426f16c298196aba733d720a92d0854bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559990"
---
# <a name="assign-a-per-user-archiving-policy-in-lync-server-2013"></a>Affectation d’une stratégie d’archivage par utilisateur dans Lync Server 2013

 


La stratégie d’archivage est l’un des paramètres individuels d’un compte d’utilisateur que vous pouvez configurer dans le panneau de configuration Lync Server 2013.

Le déploiement d’une ou de plusieurs stratégies d’archivage par utilisateur est facultatif. Vous pouvez également déployer une stratégie d’archivage uniquement au niveau global ou au niveau d’un site. Si vous déployez des stratégies au niveau utilisateur, vous devez les attribuer de manière explicite aux objets User, Group ou Contact. Les conditions requises pour l’archivage sont automatiquement définies par défaut sur celles de la stratégie de conférence de niveau global si aucune stratégie par utilisateur ou au niveau d’un site spécifique n’est attribuée.

Après avoir créé au moins une stratégie d’archivage par utilisateur, utilisez les procédures de cette rubrique pour attribuer la stratégie qui précise de manière appropriée si les communications internes, les communications externes d’un utilisateur particulier ou les deux seront archivées par le serveur.

Pour plus d’informations sur la création de stratégies d’archivage par utilisateur, reportez-vous à la rubrique [création d’une stratégie d’archivage dans Lync Server 2013 pour activer ou désactiver l’archivage des communications internes ou externes pour des sites ou des utilisateurs spécifiques](lync-server-2013-create-archiving-policy-sites-users.md).

## <a name="to-assign-a-per-user-archiving-policy"></a>Pour attribuer une stratégie d’archivage par utilisateur

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
    > Si vous voulez que la même stratégie d’archivage par utilisateur s’applique à plusieurs utilisateurs, sélectionnez-les dans les résultats de la recherche, cliquez sur <STRONG>Actions</STRONG>, puis sur <STRONG>Attribuer des stratégies</STRONG>.



7.  Dans **Attribuer des stratégies**, sous **Stratégie d’archivage**, effectuez l’une des opérations suivantes :
    

    > [!NOTE]  
    > Étant donné qu’il existe plusieurs stratégies que vous pouvez configurer à l’aide de la boîte de dialogue <STRONG>affecter les stratégies</STRONG> , l’option <STRONG> &lt; conserver en tant que est &gt; </STRONG> sélectionnée par défaut pour chaque stratégie dans la boîte de dialogue. Continuez à utiliser la stratégie précédemment attribuée à l’utilisateur sans apporter de modification au paramètre.

    
      - Autoriser Lync Server 2013 à choisir automatiquement la stratégie au niveau global ou, si elle est définie, la stratégie au niveau du site.
    
      - Cliquez sur le nom d’une stratégie d’archivage par utilisateur que vous avez précédemment définie dans la page **Stratégie d’archivage**.
        

        > [!TIP]  
        > Pour vous aider à décider de la stratégie à attribuer, après avoir cliqué sur le nom d’une stratégie, cliquez sur <STRONG>Afficher</STRONG> pour afficher les droits et les autorisations associés à la stratégie.



8.  Lorsque vous avez terminé, cliquez sur **OK**.

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a>Affectation d’une stratégie d’archivage de Per-User à l’aide d’applets de commande Windows PowerShell

Vous pouvez attribuer des stratégies d’archivage par utilisateur à l’aide de Windows PowerShell et de la cmdlet **Grant-applet csarchivingpolicy** . Vous pouvez exécuter cette cmdlet à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a>Pour affecter une stratégie d’archivage par utilisateur à un seul utilisateur

  - La commande suivante assigne la stratégie d’archivage par utilisateur RedmondArchivingPolicy à l’utilisateur Ken Myer.
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a>Pour affecter une stratégie d’archivage par utilisateur à plusieurs utilisateurs

  - Cette commande assigne la stratégie d’archivage par utilisateur RedmondArchivingPolicy à tous les utilisateurs qui ont un compte hébergé sur le pool de serveurs d’inscriptions atl-cs-001.litwareinc.com. Pour plus d’informations sur le paramètre Filter utilisé dans cette commande, reportez-vous à la documentation de la cmdlet [Get-Csuser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

## <a name="to-unassign-a-per-user-archiving-policy"></a>Pour annuler l’affectation d’une stratégie d’archivage par utilisateur

  - La commande suivante annule l’assignation d’une stratégie d’archivage par utilisateur précédemment affectée à Ken Myer. Lorsque cette stratégie par utilisateur n’est plus assignée à Ken Myer, celui-ci est géré automatiquement par la stratégie globale ou, le cas échéant, par la stratégie de site locale associée. La stratégie de site est prioritaire sur la stratégie globale.
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Grant-applet csarchivingpolicy](https://technet.microsoft.com/library/gg398475\(v=ocs.15\)) .

## <a name="see-also"></a>Voir aussi


[Création d’une stratégie d’archivage dans Lync Server 2013 pour activer ou désactiver l’archivage des communications internes ou externes pour des sites ou utilisateurs spécifiques](lync-server-2013-create-archiving-policy-sites-users.md)  


[Affectation de stratégies par utilisateur dans Lync Server 2013](lync-server-2013-assigning-per-user-policies.md)

