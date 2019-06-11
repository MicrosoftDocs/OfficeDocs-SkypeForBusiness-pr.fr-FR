---
title: 'Lync Server 2013: affecter une stratégie de conférence par utilisateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user conferencing policy
ms:assetid: 72f12c72-65f7-44fe-ab81-0f57cb2f87d1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521015(v=OCS.15)
ms:contentKeyID: 48184475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9dbeb129ef58c6993d1cd919b03d7417d35b439a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838918"
---
# <a name="assign-a-per-user-conferencing-policy-in-lync-server-2013"></a>Affecter une stratégie de conférence par utilisateur dans Lync Server 2013

 


La stratégie de conférence est l’un des paramètres individuels d’un compte d’utilisateur que vous pouvez configurer dans le panneau de configuration de Lync Server.

Le déploiement d’une ou plusieurs stratégies de conférence par utilisateur est facultatif. Vous pouvez également déployer uniquement une stratégie de conférence de niveau global ou une stratégie de conférence au niveau du site. Si vous déployez des stratégies par utilisateur, vous devez les affecter explicitement aux utilisateurs, groupes ou objets de contact. Les autorisations et privilèges d’utilisateur de la Conférence par défaut sont automatiquement définis dans la stratégie de conférence au niveau global lorsqu’aucune stratégie spécifique de niveau de site ou d’utilisateur n’est affectée.

Après avoir créé au moins une stratégie de conférence par utilisateur, suivez les procédures décrites dans cette rubrique pour affecter la stratégie qui spécifie les droits d’utilisateur et les autorisations que le serveur doit accorder aux réunions organisées par un utilisateur particulier.

Pour obtenir la liste de tous les paramètres de stratégie de conférence disponibles, voir [référence des paramètres de stratégie de conférence pour Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).

Pour plus d’informations sur la création de stratégies de conférence, voir [créer ou modifier une stratégie de conférence dans Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).

## <a name="to-assign-a-per-user-conferencing-policy"></a>Pour attribuer une stratégie de conférence par utilisateur

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
    > Si vous voulez appliquer la même stratégie de conférence par utilisateur à plusieurs utilisateurs, sélectionnez plusieurs utilisateurs dans les résultats de la recherche, cliquez sur <STRONG>actions</STRONG>, puis sur <STRONG>affecter des stratégies</STRONG>.



7.  Dans **affecter des stratégies**, sous **stratégie de conférence**, effectuez l’une des opérations suivantes:
    

    > [!NOTE]  
    > Dans la mesure où il existe plusieurs stratégies que vous pouvez configurer dans <STRONG>affecter des stratégies</STRONG>, <STRONG> &lt;l’option rester&gt; en</STRONG> cours est activée par défaut pour chaque stratégie dans la boîte de dialogue. Continuez à utiliser la stratégie précédemment attribuée à l’utilisateur sans apporter de modification au paramètre.

    
      - Sélectionnez ** \<automatique\> ** pour permettre à Lync Server 2013 de choisir automatiquement la stratégie de niveau global ou, s’il est défini, la stratégie au niveau du site.
    
      - Cliquez sur le nom d’une stratégie de conférence par utilisateur que vous avez précédemment définie dans la page **stratégie de conférence** .
        

        > [!TIP]  
        > Pour vous aider à décider quelle stratégie attribuer, après avoir cliqué sur un nom de stratégie, cliquez sur <STRONG>Afficher</STRONG> pour afficher les droits et autorisations des utilisateurs définis dans la stratégie.



8.  Lorsque vous avez terminé, cliquez sur **OK**.

## <a name="assigning-a-per-user-conferencing-policy-by-using-windows-powershell-cmdlets"></a>Attribution d’une stratégie de conférence par utilisateur à l’aide des applets de cmdlet Windows PowerShell

Les stratégies de conférence par utilisateur peuvent être affectées à l’aide de Windows PowerShell et de l’applet de passe Grant-CsConferencingPolicy. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell».

## <a name="to-assign-a-per-user-conferencing-policy-to-a-single-user"></a>Pour attribuer une stratégie de conférence par utilisateur à un utilisateur unique

  - La commande suivante affecte le RedmondConferencingPolicy de stratégie de conférence par utilisateur à l’utilisateur Ken Myer.
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName "RedmondConferencingPolicy"

## <a name="to-assign-a-per-user-conferencing-policy-to-multiple-users"></a>Pour attribuer une stratégie de conférence par utilisateur à plusieurs utilisateurs

  - Cette commande affecte la stratégie de conférence HRConferencingPolicy à tous les utilisateurs qui travaillent pour le service de ressources humaines. Pour plus d’informations sur le paramètre LdapFilter utilisé dans cette commande, voir la documentation relative à l’applet de commande [Get-Csuser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -LdapFilter "Department=Human Resources" | Grant-CsConferencingPolicy -PolicyName "HRConferencingPolicy"

## <a name="to-unassign-a-per-user-conferencing-policy"></a>Pour annuler l’affectation d’une stratégie de conférence par utilisateur

  - La commande suivante annule l’attribution d’une stratégie de conférence par utilisateur précédemment attribuée à Ken Myer. Une fois l’affectation de la stratégie par utilisateur annulée, Ken Myer sera automatiquement géré en utilisant la stratégie globale ou, le cas échéant, sa stratégie de site local. Une stratégie de site est prioritaire sur la stratégie globale.
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName $Null

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de passe [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg425937\(v=ocs.15\)) .

## <a name="see-also"></a>Voir aussi


[Création ou modification d’une stratégie de conférence dans Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md)  


[Attribution de stratégies par utilisateur dans Lync Server 2013](lync-server-2013-assigning-per-user-policies.md)

