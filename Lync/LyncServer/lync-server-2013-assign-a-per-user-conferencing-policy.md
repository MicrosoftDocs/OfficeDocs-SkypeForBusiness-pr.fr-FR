---
title: 'Lync Server 2013 : affecter une stratégie de conférence par utilisateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user conferencing policy
ms:assetid: 72f12c72-65f7-44fe-ab81-0f57cb2f87d1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521015(v=OCS.15)
ms:contentKeyID: 48184475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47419dfde4bf41b0edfccb2bce23393f04c49a3d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134450"
---
# <a name="assign-a-per-user-conferencing-policy-in-lync-server-2013"></a>Affecter une stratégie de conférence par utilisateur dans Lync Server 2013

 


La stratégie de conférence est l’un des paramètres individuels d’un compte d’utilisateur que vous pouvez configurer dans le panneau de configuration Lync Server.

Le déploiement d’une ou plusieurs stratégies de conférence par utilisateur est facultatif. Vous pouvez également déployer une stratégie de conférence au niveau global ou au niveau d’un site. Si vous déployez des stratégies au niveau utilisateur, vous devez les attribuer de manière explicite à des utilisateurs, des groupes ou des objets contact. Les droits et autorisations des utilisateurs de conférence sont automatiquement définis sur ceux de la stratégie de conférence globale si aucune stratégie par utilisateur ou au niveau d’un site spécifique n’est attribuée.

Lorsque vous aurez créé au moins une stratégie de conférence par utilisateur, suivez les procédures de cette rubrique pour attribuer la stratégie spécifiant les droits et autorisations que le serveur doit octroyer aux réunions organisées par un utilisateur particulier.

Pour obtenir la liste de tous les paramètres de stratégie de conférence disponibles, consultez la rubrique [référence des paramètres de stratégie de conférence pour Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).

Pour plus d’informations sur la création de stratégies de conférence, voir [Create or Modify a Conferencing Policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).

## <a name="to-assign-a-per-user-conferencing-policy"></a>Pour attribuer une stratégie de conférence par utilisateur

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
    > Si vous voulez que la même stratégie de conférence par utilisateur s’applique à plusieurs utilisateurs, sélectionnez-les dans les résultats de la recherche, cliquez sur <STRONG>Actions</STRONG>, puis sur <STRONG>Attribuer des stratégies</STRONG>.



7.  Dans **Attribuer des stratégies**, sous **Stratégie de conférence**, effectuez l’une des opérations suivantes :
    

    > [!NOTE]  
    > Étant donné qu’il existe plusieurs stratégies que vous pouvez configurer dans <STRONG>affecter des stratégies</STRONG>, <STRONG> &lt;garder en&gt; tant que est</STRONG> sélectionnée par défaut pour chaque stratégie dans la boîte de dialogue. Continuez à utiliser la stratégie précédemment attribuée à l’utilisateur sans apporter de modification au paramètre.

    
      - Sélectionnez ** \<automatique\> ** pour permettre à Lync Server 2013 de choisir automatiquement la stratégie au niveau global ou, si elle est définie, la stratégie au niveau du site.
    
      - Cliquez sur le nom d’une stratégie de conférence par utilisateur que vous avez précédemment définie dans la page **Stratégie de conférence**.
        

        > [!TIP]  
        > Pour vous aider à décider quelle stratégie attribuer, après avoir cliqué sur un nom de stratégie, cliquez sur <STRONG>Afficher</STRONG> pour afficher les droits et autorisations des utilisateurs définis dans la stratégie.



8.  Lorsque vous avez terminé, cliquez sur **OK**.

## <a name="assigning-a-per-user-conferencing-policy-by-using-windows-powershell-cmdlets"></a>Affectation d’une stratégie de conférence par utilisateur à l’aide d’applets de commande Windows PowerShell

Les stratégies de conférence par utilisateur peuvent être affectées à l’aide de Windows PowerShell et de la cmdlet Grant-CsConferencingPolicy. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.

## <a name="to-assign-a-per-user-conferencing-policy-to-a-single-user"></a>Pour affecter une stratégie de conférence par utilisateur à un seul utilisateur

  - La commande suivante affecte la stratégie de conférence par utilisateur RedmondConferencingPolicy à l’utilisateur Ken Myer.
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName "RedmondConferencingPolicy"

## <a name="to-assign-a-per-user-conferencing-policy-to-multiple-users"></a>Pour affecter une stratégie de conférence par utilisateur à plusieurs utilisateurs

  - Cette commande affecte la stratégie de conférence par utilisateur HRConferencingPolicy à tous les utilisateurs qui travaillent pour le service des ressources humaines. Pour plus d’informations sur le paramètre LdapFilter utilisé dans cette commande, reportez-vous à la documentation de la cmdlet [Get-Csuser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -LdapFilter "Department=Human Resources" | Grant-CsConferencingPolicy -PolicyName "HRConferencingPolicy"

## <a name="to-unassign-a-per-user-conferencing-policy"></a>Pour annuler l’affectation d’une stratégie de conférence par utilisateur

  - La commande suivante annule l’affectation d’une stratégie de conférence par utilisateur précédemment affectée à Ken Myer. Lorsque cette stratégie par utilisateur n’est plus affectée à Ken Myer, celui-ci est automatiquement géré par la stratégie globale ou, le cas échéant, par la stratégie de site locale associée. La stratégie de site est prioritaire sur la stratégie globale.
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName $Null

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\)) .

## <a name="see-also"></a>Voir aussi


[Création ou modification d’une stratégie de conférence dans Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md)  


[Affectation de stratégies par utilisateur dans Lync Server 2013](lync-server-2013-assigning-per-user-policies.md)

