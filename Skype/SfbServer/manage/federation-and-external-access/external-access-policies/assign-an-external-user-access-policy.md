---
title: Attribution d’une stratégie d’accès des utilisateurs externes
ms.reviewer: ''
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Si un utilisateur a été activé pour Skype entreprise Server, vous pouvez configurer la Fédération SIP, l’accès à l’utilisateur distant et la connectivité de messagerie instantanée publique dans le panneau de configuration Skype entreprise Server en appliquant les stratégies appropriées à des utilisateurs spécifiques.
ms.openlocfilehash: b87eb377b23063dbcdfd9562a99533da230a8f30
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818325"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a>Affectation d’une stratégie d’accès utilisateur externe à un utilisateur de Skype entreprise

Si un utilisateur a été activé pour Skype entreprise Server, vous pouvez configurer la Fédération SIP, l’accès à l’utilisateur distant et la connectivité de messagerie instantanée publique dans le panneau de configuration Skype entreprise Server en appliquant les stratégies appropriées à des utilisateurs spécifiques. Par exemple, si vous avez créé une stratégie pour prendre en charge l’accès des utilisateurs distants, vous devez l’appliquer à l’utilisateur avant de pouvoir se connecter à Skype entreprise Server à partir d’un emplacement distant et collaborer avec des utilisateurs internes à partir de l’emplacement distant.


> [!NOTE]  
> Pour prendre en charge l’accès utilisateur externe, vous devez activer la prise en charge de chaque type d’accès des utilisateurs externes que vous voulez prendre en charge, et configurer les stratégies et autres options appropriées pour contrôler son utilisation. Pour plus d’informations, reportez-vous [à gestion de la Fédération et accès externe à Skype entreprise Server](../managing-federation-and-external-access.md).


Suivez la procédure décrite dans cette rubrique pour appliquer une stratégie d’accès aux utilisateurs externes précédemment créée à un ou plusieurs comptes d’utilisateurs.


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>Pour appliquer une stratégie d’utilisateur externe à un compte d’utilisateur

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur à configurer.

4.  Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans **modifier l’utilisateur de Skype entreprise Server** sous **stratégie d’accès externe**, sélectionnez la stratégie d’utilisateur que vous voulez appliquer.
     
> [!NOTE]  
> Les paramètres de ** \<>automatiques** appliquent le serveur par défaut ou les paramètres de stratégie globale.


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>Attribution de stratégies d’accès externe par utilisateur à l’aide des applets de cmdlet Windows PowerShell

Les stratégies d’accès externe par utilisateur peuvent être affectées à l’aide de Windows PowerShell et de l’applet de passe Grant-CsExternalAccessPolicy. Cette applet de commande peut être exécutée à partir de Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell. 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>Pour attribuer une stratégie d’accès externe par utilisateur à un utilisateur unique

  - Cette commande affecte le RedmondExternalAccessPolicy de stratégie d’accès externe par utilisateur à l’utilisateur Ken Myer.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>Pour attribuer une stratégie d’accès externe par utilisateur à plusieurs utilisateurs

  - Cette commande affecte le USAExternalAccessPolicy de stratégie d’accès externe par utilisateur à tous les utilisateurs possédant des comptes dans l’unité d’organisation américaine d’Active Directory. Pour plus d’informations sur le paramètre de l’unité d’organisation utilisée dans cette commande, voir la documentation relative à l’applet de commande [Get-Csuser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) .
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a>Pour annuler l’affectation d’une stratégie d’accès externe par utilisateur

  - Cette commande annule l’affectation d’une stratégie d’accès externe par utilisateur précédemment affectée à Ken Myer. Une fois l’affectation de la stratégie par utilisateur annulée, Ken Myer sera automatiquement géré en utilisant la stratégie globale ou, le cas échéant, sa stratégie de site local. Une stratégie de site est prioritaire sur la stratégie globale.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null



Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de passe [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy) .


