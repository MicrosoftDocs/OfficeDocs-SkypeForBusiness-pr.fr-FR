---
title: 'Lync Server 2013: affecter une stratégie de version de client par utilisateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user client version policy
ms:assetid: f7e8ba2f-62dc-4e7d-8b63-682986f10240
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182607(v=OCS.15)
ms:contentKeyID: 48185868
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bfd26aff4ae2e5d8dacf7ec145bec0e3247facf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838753"
---
# <a name="assign-a-per-user-client-version-policy-in-lync-server-2013"></a>Affecter une stratégie de version de client par utilisateur dans Lync Server 2013

 


La stratégie de version du client est l’un des paramètres individuels d’un compte d’utilisateur que vous pouvez configurer dans le panneau de configuration de Lync Server.

Le déploiement d’une ou plusieurs stratégies de version de client par utilisateur est facultatif. Vous pouvez également déployer uniquement une stratégie de version de client de niveau global, ou des stratégies de version de client de niveau de site ou de groupe. Si vous déployez des stratégies au niveau utilisateur, vous devez les attribuer de manière explicite aux objets User, Group ou Contact. S’il n’y a pas d’attribution de stratégies de niveau de site, de pool ou par utilisateur spécifiques, les clients par défaut autorisés à s’inscrire auprès de Lync Server 2013 sont ceux définis dans la stratégie de version de client de niveau global.

Après avoir créé au moins une stratégie de version de client par utilisateur, suivez les procédures décrites dans cette rubrique pour affecter la stratégie spécifiant les versions de clients que vous voulez autoriser à inscrire sur Lync Server.

Pour plus d’informations sur la création de stratégies de version de client par utilisateur, voir [spécification des applications clientes qui peuvent être utilisées pour la connexion à Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md).

## <a name="to-assign-a-per-user-client-version-policy"></a>Pour attribuer une stratégie de version de client par utilisateur

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
    > Si vous voulez appliquer la même stratégie de version de client par utilisateur à plusieurs utilisateurs, sélectionnez plusieurs utilisateurs dans les résultats de la recherche, cliquez sur <STRONG>actions</STRONG>, puis sur <STRONG>affecter des stratégies</STRONG>.



7.  Dans **affecter des stratégies**, sous **stratégie de version de client**, effectuez l’une des opérations suivantes:
    

    > [!NOTE]  
    > Dans la mesure où il existe plusieurs stratégies que vous pouvez configurer à l’aide de la boîte de dialogue <STRONG>affecter des stratégies</STRONG> , <STRONG> &lt;l’option conserver en tant que est&gt; </STRONG> activée par défaut pour chaque stratégie dans la boîte de dialogue. Continuez à utiliser la stratégie précédemment attribuée à l’utilisateur sans apporter de modification au paramètre.

    
      - Autorisez le serveur Lync à choisir automatiquement la stratégie de niveau global ou, si elle est définie, la stratégie de niveau du site ou la stratégie de niveau groupe.
    
      - Cliquez sur le nom d’une stratégie de version de client par utilisateur que vous avez précédemment définie sur la page de **stratégie de version du client** .
        

        > [!TIP]  
        > Pour vous aider à décider quelle stratégie attribuer, après avoir cliqué sur un nom de stratégie, cliquez sur <STRONG>Afficher</STRONG> pour afficher les droits et autorisations des utilisateurs définis dans la stratégie.



8.  Lorsque vous avez terminé, cliquez sur **OK**.

## <a name="assigning-a-per-user-client-version-policy-by-using-windows-powershell-cmdlets"></a>Attribution d’une stratégie de version de client par utilisateur à l’aide des cmdlets Windows PowerShell

Vous pouvez affecter des stratégies de version de client par utilisateur à l’aide de l’applet de contrôle Grant-CsClientVersionPolicy. Vous pouvez exécuter cette applet de commande sur Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell».

## <a name="to-assign-a-per-user-client-version-policy-to-a-single-user"></a>Pour attribuer une stratégie de version de client par utilisateur à un utilisateur unique

  - La commande suivante assigne le RedmondClientVersionPolicy de la stratégie de version du client par utilisateur à l’utilisateur Ken Myer.
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName "RedmondClientVersionPolicy"

## <a name="to-assign-a-per-user-client-version-policy-to-multiple-users"></a>Pour attribuer une stratégie de version de client par utilisateur à plusieurs utilisateurs

  - Cette commande affecte la stratégie de version de client RedmondClientVersionPolicy à tous les utilisateurs auxquels est actuellement affectée le RedmondVoicePolicy de la stratégie vocale. Pour plus d’informations sur le paramètre de filtre utilisé dans cette commande, consultez la documentation de l’applet de commande [Get-Csuser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -Filter {VoicePolicy -eq "RedmondVoicePolicy"} | Grant-CsClientVersionPolicy -PolicyName "RedmondClientVersionPolicy"

## <a name="to-unassign-a-per-user-client-version-policy"></a>Pour annuler l’affectation d’une stratégie de version de client par utilisateur

  - La commande suivante annule l’affectation d’une stratégie de version de client par utilisateur précédemment attribuée à Ken Myer. Après l’affectation de la stratégie par utilisateur, Ken Myer sera automatiquement géré à l’aide de la stratégie globale, de sa stratégie de site local (s’il en existe une) ou de la stratégie de portée de service attribuée à son bureau d’enregistrement. Une stratégie d’étendue de service est prioritaire sur n’importe quelle stratégie de site, et une stratégie de site est prioritaire par rapport à la stratégie globale.
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName $Null

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de passe [Grant-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/gg412903\(v=ocs.15\)) .

## <a name="see-also"></a>Voir aussi


[Attribution de stratégies par utilisateur dans Lync Server 2013](lync-server-2013-assigning-per-user-policies.md)  
[Gestion des appareils, des téléphones et des applications client dans Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)

