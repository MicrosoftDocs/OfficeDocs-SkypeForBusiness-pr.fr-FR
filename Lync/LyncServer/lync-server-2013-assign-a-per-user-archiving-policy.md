---
title: 'Lync Server 2013 : affecter une stratégie d’archivage par utilisateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user archiving policy
ms:assetid: a12ca483-b235-460f-b3fe-130fb3087264
ms:mtpsurl: https://technet.microsoft.com/library/Gg182560(v=OCS.15)
ms:contentKeyID: 48185014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36d23e44e397a77f0d490d8fda27ee711d1c61c5
ms.sourcegitcommit: 0119af282f53f49c4ab6e01c3319d01bc6fdad2c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/14/2020
ms.locfileid: "41111578"
---
# <a name="assign-a-per-user-archiving-policy-in-lync-server-2013"></a>Affecter une stratégie d’archivage par utilisateur dans Lync Server 2013

 


La stratégie d’archivage est l’un des paramètres individuels d’un compte d’utilisateur que vous pouvez configurer dans le panneau de configuration de Lync Server 2013.

Le déploiement d’une ou plusieurs stratégies d’archivage par utilisateur est facultatif. Vous pouvez également déployer uniquement une stratégie d’archivage au niveau mondial ou une stratégie d’archivage au niveau du site. Si vous déployez des stratégies au niveau utilisateur, vous devez les attribuer de manière explicite aux objets User, Group ou Contact. Les exigences d’archivage définies automatiquement par défaut par celles définies dans la stratégie de conférence au niveau global s’il n’y a pas d’attribution de stratégies de niveau de site ou d’utilisateur spécifiques.

Après avoir créé au moins une stratégie d’archivage par utilisateur, suivez les procédures décrites dans cette rubrique pour affecter la stratégie qui détermine de manière appropriée si les communications internes d’un utilisateur particulier ou les deux sont archivées par le serveur.

Pour plus d’informations sur la création de stratégies d’archivage par utilisateur, reportez-vous à la rubrique [création d’une stratégie d’archivage dans Lync Server 2013 pour activer ou désactiver l’archivage des communications internes ou externes pour des sites ou des utilisateurs spécifiques](lync-server-2013-create-archiving-policy-sites-users.md).

## <a name="to-assign-a-per-user-archiving-policy"></a>Pour attribuer une stratégie d’archivage par utilisateur

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
    > Si vous voulez appliquer la même stratégie d’archivage par utilisateur à plusieurs utilisateurs, sélectionnez plusieurs utilisateurs dans les résultats de la recherche, cliquez sur <STRONG>actions</STRONG>, puis sur <STRONG>affecter des stratégies</STRONG>.



7.  Dans **affecter des stratégies**, sous **stratégie d’archivage**, effectuez l’une des opérations suivantes :
    

    > [!NOTE]  
    > Dans la mesure où il existe plusieurs stratégies que vous pouvez configurer à l’aide de la boîte de dialogue <STRONG>affecter des stratégies</STRONG> , <STRONG> &lt;l’option conserver en tant que est&gt; </STRONG> activée par défaut pour chaque stratégie dans la boîte de dialogue. Continuez à utiliser la stratégie précédemment attribuée à l’utilisateur sans apporter de modification au paramètre.

    
      - Autorisez Lync Server 2013 à choisir automatiquement la stratégie de niveau global ou, s’il est défini, la stratégie au niveau du site.
    
      - Cliquez sur le nom d’une stratégie d’archivage par utilisateur que vous avez précédemment définie dans la page **stratégie d’archivage** .
        

        > [!TIP]  
        > Pour vous aider à décider de la stratégie que vous voulez attribuer, après avoir cliqué sur un nom de stratégie, cliquez sur <STRONG>Afficher</STRONG> pour afficher les droits d’utilisateur et les autorisations définis dans la stratégie.



8.  Lorsque vous avez terminé, cliquez sur **OK**.

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a>Attribution d’une stratégie d’archivage par utilisateur à l’aide des applets de cmdlet Windows PowerShell

Vous pouvez attribuer des stratégies d’archivage par utilisateur à l’aide de Windows PowerShell et de l’applet **de passe Grant-CsArchivingPolicy** . Vous pouvez exécuter cette applet de commande sur Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a>Pour attribuer une stratégie d’archivage par utilisateur à un utilisateur unique

  - La commande suivante assigne la stratégie d’archivage par utilisateur RedmondArchivingPolicy à l’utilisateur Ken Myer.
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a>Pour attribuer une stratégie d’archivage par utilisateur à plusieurs utilisateurs

  - Cette commande affecte le RedmondArchivingPolicy de stratégie d’archivage par utilisateur à tous les utilisateurs disposant de comptes hébergés sur le pool d’inscriptions atl-cs-001.litwareinc.com. Pour plus d’informations sur le paramètre de filtre utilisé dans cette commande, consultez la documentation de l’applet de commande [Get-Csuser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

## <a name="to-unassign-a-per-user-archiving-policy"></a>Pour annuler l’affectation d’une stratégie d’archivage par utilisateur

  - La commande suivante réattribue toutes les stratégies d’archivage par utilisateur précédemment affectées à Ken Myer. Une fois l’affectation de la stratégie par utilisateur annulée, Ken Myer sera automatiquement géré en utilisant la stratégie globale ou, le cas échéant, sa stratégie de site local. Une stratégie de site est prioritaire sur la stratégie globale.
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de passe [Grant-CsArchivingPolicy](https://technet.microsoft.com/library/gg398475\(v=ocs.15\)) .

## <a name="see-also"></a>Voir aussi


[Création d’une stratégie d’archivage dans Lync Server 2013 pour activer ou désactiver l’archivage des communications internes ou externes pour des sites ou des utilisateurs spécifiques](lync-server-2013-create-archiving-policy-sites-users.md)  


[Attribution de stratégies par utilisateur dans Lync Server 2013](lync-server-2013-assigning-per-user-policies.md)

