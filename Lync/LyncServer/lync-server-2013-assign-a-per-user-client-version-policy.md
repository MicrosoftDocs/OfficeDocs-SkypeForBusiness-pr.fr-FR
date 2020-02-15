---
title: 'Lync Server 2013 : affecter une stratégie de version de client par utilisateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user client version policy
ms:assetid: f7e8ba2f-62dc-4e7d-8b63-682986f10240
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182607(v=OCS.15)
ms:contentKeyID: 48185868
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3668e21836fd3ecee0740493c8b9bd631227583a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029265"
---
# <a name="assign-a-per-user-client-version-policy-in-lync-server-2013"></a>Affecter une stratégie de version de client par utilisateur dans Lync Server 2013

 


La stratégie de version du client est l’un des paramètres individuels d’un compte d’utilisateur que vous pouvez configurer dans le panneau de configuration Lync Server.

Le déploiement d’une ou plusieurs stratégies de version du client par utilisateur est facultatif. Vous pouvez également ne déployer qu’une stratégie de version du client au niveau global, ou encore déployer des stratégies de version du client au niveau du site ou du pool. Si vous déployez des stratégies au niveau utilisateur, vous devez les attribuer de manière explicite aux objets User, Group ou Contact. Lorsqu’aucune stratégie spécifique au niveau du site, du pool ou par utilisateur n’est affectée, les clients par défaut autorisés à s’inscrire auprès de Lync Server 2013 sont ceux définis dans la stratégie de version du client au niveau global.

Après avoir créé au moins une stratégie de version de client par utilisateur, utilisez les procédures de cette rubrique pour affecter la stratégie qui spécifie les versions du client que vous souhaitez autoriser à s’inscrire auprès de Lync Server.

Pour plus d’informations sur la création de stratégies de version de client par utilisateur, voir [spécification des applications clientes pouvant être utilisées pour se connecter à Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md).

## <a name="to-assign-a-per-user-client-version-policy"></a>Pour affecter une stratégie de version du client par utilisateur

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
    > Si vous voulez que la même stratégie de version du client par utilisateur s’applique à plusieurs utilisateurs, sélectionnez plusieurs utilisateurs dans les résultats de la recherche, puis cliquez sur <STRONG>Actions</STRONG> et sur <STRONG>Attribuer des stratégies</STRONG>.



7.  Dans **Attribuer des stratégies**, sous **Stratégie de version du client**, effectuez l’une des opérations suivantes :
    

    > [!NOTE]  
    > Étant donné qu’il existe plusieurs stratégies que vous pouvez configurer à l’aide de la boîte de dialogue <STRONG>affecter les stratégies</STRONG> , <STRONG> &lt;l’option conserver en tant que est&gt; </STRONG> sélectionnée par défaut pour chaque stratégie dans la boîte de dialogue. Continuez à utiliser la stratégie précédemment attribuée à l’utilisateur sans apporter de modification au paramètre.

    
      - Autoriser Lync Server à choisir automatiquement la stratégie au niveau global ou, si elle est définie, la stratégie au niveau du site ou la stratégie au niveau du pool.
    
      - Cliquez sur le nom d’une stratégie de version du client par utilisateur que vous avez précédemment définie sur la page **Stratégie de version du client**.
        

        > [!TIP]  
        > Pour vous aider à décider quelle stratégie attribuer, après avoir cliqué sur un nom de stratégie, cliquez sur <STRONG>Afficher</STRONG> pour afficher les droits et autorisations des utilisateurs définis dans la stratégie.



8.  Lorsque vous avez terminé, cliquez sur **OK**.

## <a name="assigning-a-per-user-client-version-policy-by-using-windows-powershell-cmdlets"></a>Affectation d’une stratégie de version de client par utilisateur à l’aide d’applets de commande Windows PowerShell

Vous pouvez affecter des stratégies de version du client par utilisateur en utilisant la cmdlet Grant-CsClientVersionPolicy cmdlet. Vous pouvez exécuter cette applet de commande à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.

## <a name="to-assign-a-per-user-client-version-policy-to-a-single-user"></a>Pour affecter une stratégie de version du client par utilisateur à un seul utilisateur

  - La commande suivante affecte la stratégie de version du client par utilisateur RedmondClientVersionPolicy à l’utilisateur Ken Myer.
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName "RedmondClientVersionPolicy"

## <a name="to-assign-a-per-user-client-version-policy-to-multiple-users"></a>Pour affecter une stratégie de version du client par utilisateur à plusieurs utilisateurs

  - Cette commande affecte la stratégie de version du client par utilisateur RedmondClientVersionPolicy à tous les utilisateurs actuellement affectés à la stratégie vocale RedmondVoicePolicy. Pour plus d’informations sur le paramètre Filter utilisé dans cette commande, reportez-vous à la documentation de la cmdlet [Get-Csuser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -Filter {VoicePolicy -eq "RedmondVoicePolicy"} | Grant-CsClientVersionPolicy -PolicyName "RedmondClientVersionPolicy"

## <a name="to-unassign-a-per-user-client-version-policy"></a>Pour annuler l’affectation d’une stratégie de version du client par utilisateur

  - La commande suivante annule l’affectation de toute stratégie de version du client par utilisateur affectée à Ken Myer. Une fois l’affectation de la stratégie par utilisateur annulée, Ken Myer sera automatiquement géré en utilisant la stratégie globale, sa stratégie de site locale (le cas échéant), ou la stratégie d’étendue de service affectée à son serveur d’inscription. Une stratégie d’étendue de service est prioritaire sur les stratégies de site, et une stratégie de site est prioritaire sur la stratégie globale.
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName $Null

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Grant-CsClientVersionPolicy](https://technet.microsoft.com/library/gg412903\(v=ocs.15\)) .

## <a name="see-also"></a>Voir aussi


[Affectation de stratégies par utilisateur dans Lync Server 2013](lync-server-2013-assigning-per-user-policies.md)  
[Gestion des appareils, des téléphones et des applications clientes dans Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)

