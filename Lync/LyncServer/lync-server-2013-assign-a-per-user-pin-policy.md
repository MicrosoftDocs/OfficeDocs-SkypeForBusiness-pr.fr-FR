---
title: 'Lync Server 2013: affecter une stratégie de code confidentiel par utilisateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user PIN policy
ms:assetid: d8211c64-0b63-4193-a074-673da7d14287
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182594(v=OCS.15)
ms:contentKeyID: 48185475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c60943ad13bd03de6e4474ec35f2deea1964bad
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846898"
---
# <a name="assign-a-per-user-pin-policy-in-lync-server-2013"></a>Affecter une stratégie de code confidentiel par utilisateur dans Lync Server 2013

 


La stratégie code confidentiel (PIN) pour les conférences rendez-vous est l’un des paramètres individuels d’un compte d’utilisateur qui peuvent être configurés dans le panneau de configuration de Lync Server 2013.

Le déploiement d’une ou plusieurs stratégies de code confidentiel par utilisateur est facultatif. Vous pouvez également déployer une stratégie de code confidentiel au niveau global ou au niveau d’un site. Si vous déployez des stratégies au niveau utilisateur, vous devez les attribuer de manière explicite aux objets User, Group ou Contact. Les droits et autorisations des utilisateurs concernant l’utilisation des codes confidentiels pour les conférences rendez-vous sont automatiquement définis sur ceux de la stratégie de code confidentiel globale si aucune stratégie par utilisateur ou au niveau d’un site spécifique n’est attribuée.

Lorsque vous aurez créé au moins une stratégie de code confidentiel par utilisateur, suivez les procédures de cette rubrique pour attribuer la stratégie spécifiant les contraintes que le serveur doit appliquer aux codes confidentiels créés et utilisés par un utilisateur particulier.

Pour plus d’informations sur la création de stratégies de code confidentiel de conférence rendez-vous par utilisateur, voir [créer ou modifier les paramètres de code confidentiel de conférence rendez-vous dans Lync Server 2013 pour un site ou un groupe d’utilisateurs](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md).

## <a name="to-assign-a-per-user-pin-policy"></a>Pour attribuer une stratégie de code confidentiel par utilisateur

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
    > Si vous voulez que la même stratégie de code confidentiel par utilisateur s’applique à plusieurs utilisateurs, sélectionnez-les dans les résultats de la recherche, cliquez sur <STRONG>Actions</STRONG>, puis sur <STRONG>Attribuer des stratégies</STRONG>.



7.  Dans **Attribuer des stratégies**, sous **Stratégie de code confidentiel**, effectuez l’une des opérations suivantes :
    

    > [!NOTE]  
    > Dans la mesure où il existe plusieurs stratégies que vous pouvez configurer à l’aide de la boîte de dialogue <STRONG>affecter des stratégies</STRONG> , <STRONG> &lt;l’option conserver en tant que est&gt; </STRONG> activée par défaut pour chaque stratégie dans la boîte de dialogue. Continuez à utiliser la stratégie précédemment attribuée à l’utilisateur sans apporter de modification au paramètre.

    
      - Autorisez Lync Server 2013 à choisir automatiquement la stratégie de niveau global ou, s’il est défini, la stratégie au niveau du site.
    
      - Cliquez sur le nom d’une stratégie de code confidentiel par utilisateur que vous avez définie dans la page **Stratégie de code confidentiel**.
        

        > [!TIP]  
        > Pour vous aider à décider quelle stratégie attribuer, après avoir cliqué sur un nom de stratégie, cliquez sur <STRONG>Afficher</STRONG> pour afficher les droits et autorisations des utilisateurs définis dans la stratégie.



8.  Lorsque vous avez terminé, cliquez sur **OK**.

## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a>Attribution d’une stratégie de code confidentiel par utilisateur à l’aide des applets de cmdlet Windows PowerShell

Vous pouvez affecter des stratégies de code confidentiel par utilisateur à l’aide de Windows PowerShell et de l’applet **de passe Grant-CsPinPolicy** . Vous pouvez exécuter cette applet de commande sur Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell».

## <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a>Pour affecter une stratégie de code confidentiel par utilisateur à un seul utilisateur

  - La commande suivante affecte la stratégie de code confidentiel par utilisateur RedmondPinPolicy à l’utilisateur Ken Myer.
    
        Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"

## <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a>Pour affecter une stratégie de code confidentiel par utilisateur à plusieurs utilisateurs

  - La commande suivante affecte la stratégie de code confidentiel par utilisateur RedmondUsersPinPolicy à tous les utilisateurs travaillant dans la ville de Redmond. Pour plus d’informations sur le paramètre LdapFilter utilisé dans cette commande, voir [Get-Csuser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)).
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"

## <a name="to-unassign-a-per-user-pin-policy"></a>Pour annuler l’affectation d’une stratégie de code confidentiel par utilisateur

  - La commande suivante annule l’affectation d’une stratégie de code confidentiel par utilisateur précédemment affectée à Ken Myer. Une fois l’affectation de la stratégie par utilisateur annulée, Ken Myer sera automatiquement géré en utilisant la stratégie globale ou, le cas échéant, sa stratégie de site local. Une stratégie de site est prioritaire sur la stratégie globale.
    
        Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null

Pour plus d’informations, consultez la rubrique [Grant-CsPinPolicy](https://technet.microsoft.com/en-us/library/gg398871\(v=ocs.15\)).

## <a name="see-also"></a>Voir aussi


[Créer une nouvelle stratégie de code confidentiel dans Lync Server 2013](lync-server-2013-create-a-new-pin-policy.md)  


[Attribution de stratégies par utilisateur dans Lync Server 2013](lync-server-2013-assigning-per-user-policies.md)

