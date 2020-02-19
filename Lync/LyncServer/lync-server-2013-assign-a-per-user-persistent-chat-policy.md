---
title: 'Lync Server 2013 : affecter une stratégie de conversation permanente par utilisateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user Persistent Chat policy
ms:assetid: e22168f2-fde1-4f0a-b194-1fc881436822
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721908(v=OCS.15)
ms:contentKeyID: 49733842
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e06d6c7403bd348b44c6ab36216ed7ee9a1c6d02
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134410"
---
# <a name="assign-a-per-user-persistent-chat-policy-in-lync-server-2013"></a>Affectation d’une stratégie de conversation permanente par utilisateur dans Lync Server 2013

 


Vous pouvez affecter une stratégie de conversation permanente par utilisateur avec le panneau de configuration Lync Server 2013 ou Lync Server 2013 Management Shell. Pour plus d’informations sur la création de stratégies utilisateur pour le serveur de conversation permanente, voir [Create a User Policy for persistent chat in Lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md).

## <a name="to-assign-a-per-user-persistent-chat-policy-with-lync-server-control-panel"></a>Pour affecter une stratégie de conversation permanente par utilisateur à l’aide du panneau de configuration Lync Server

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
    > Si vous voulez que la même stratégie de conversation permanente par utilisateur s’applique à plusieurs utilisateurs, sélectionnez plusieurs utilisateurs dans les résultats de la recherche, puis cliquez sur <STRONG>actions</STRONG>et sur <STRONG>attribuer des stratégies</STRONG>.



7.  Dans **attribuer des stratégies**, sous **stratégie de conversation permanente**, effectuez l’une des opérations suivantes :
    

    > [!NOTE]  
    > Étant donné qu’il existe plusieurs stratégies que vous pouvez configurer à l’aide de la boîte de dialogue <STRONG>affecter les stratégies</STRONG> , <STRONG> &lt;l’option conserver en tant que est&gt; </STRONG> sélectionnée par défaut pour chaque stratégie dans la boîte de dialogue. Continuez à utiliser la stratégie précédemment attribuée à l’utilisateur sans apporter de modification au paramètre.

    
      - Sélectionnez ** \<automatique\> ** pour permettre à Lync Server 2013 de choisir automatiquement la stratégie au niveau global ou, si elle est définie, la stratégie au niveau du site.
    
      - Cliquez sur le nom d’une stratégie de conversation permanente par utilisateur que vous avez précédemment définie dans la page **stratégie de conversation permanente** .
        

        > [!TIP]  
        > Pour vous aider à décider quelle stratégie attribuer, après avoir cliqué sur un nom de stratégie, cliquez sur <STRONG>Afficher</STRONG> pour afficher les droits et autorisations des utilisateurs définis dans la stratégie.



8.  Lorsque vous avez terminé, cliquez sur **OK**.

## <a name="assigning-a-per-user-persistent-chat-policy-by-using-windows-powershell-cmdlets"></a>Affectation d’une stratégie de conversation permanente par utilisateur à l’aide des applets de commande Windows PowerShell

Vous pouvez également affecter des stratégies de conversation permanente par utilisateur à l’aide de la cmdlet **Grant-CsPersistentChatPolicy** . Vous pouvez exécuter cette cmdlet à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.

## <a name="to-assign-a-per-user-persistent-chat-policy-to-a-single-user"></a>Pour affecter une stratégie de conversation permanente par utilisateur à un seul utilisateur

  - La commande suivante affecte la stratégie de conversation persistante par utilisateur RedmondPersistentChatPolicy à l’utilisateur Ken Myer.
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName "RedmondPersistentChatPolicy"

## <a name="to-assign-a-per-user-persistent-chat-policy-to-multiple-users"></a>Pour affecter une stratégie de conversation permanente par utilisateur à plusieurs utilisateurs

  - Cette commande affecte la stratégie de conversation persistante par utilisateur RedmondUsersPersistentChatPolicy à tous les utilisateurs qui travaillent pour le service informatique. Pour plus d’informations sur le paramètre LdapFilter utilisé dans cette commande, reportez-vous à la documentation de la cmdlet [Get-Csuser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -LdapFilter "Department=IT" | Grant-CsPersistentChatPolicy -PolicyName "RedmondUsersPersistentChatPolicy"

## <a name="to-unassign-a-per-user-persistent-chat-policy"></a>Pour annuler l’affectation d’une stratégie de conversation permanente par utilisateur

  - La commande suivante annule l’affectation d’une stratégie de conversation permanente par utilisateur précédemment affectée à Ken Myer. Lorsque cette stratégie par utilisateur n’est plus assignée à Ken Myer, celui-ci est géré automatiquement par la stratégie globale ou, le cas échéant, par la stratégie de site locale associée. La stratégie de site est prioritaire sur la stratégie globale.
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName $Null

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Grant-CsPersistentChatPolicy](https://technet.microsoft.com/library/jj204907\(v=ocs.15\)) .

## <a name="see-also"></a>Voir aussi


[Créer une stratégie utilisateur pour la conversation permanente dans Lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

