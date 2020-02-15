---
title: Affecter une stratégie d’accès des utilisateurs externes
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
description: Si un utilisateur a été activé pour Skype entreprise Server, vous pouvez configurer la Fédération SIP, l’accès des utilisateurs distants et la connectivité PIC dans le panneau de configuration de Skype entreprise Server en appliquant les stratégies appropriées à des utilisateurs spécifiques.
ms.openlocfilehash: c03eb957679877ec512b042e0db624adbb3e6f52
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043676"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a>Affecter une stratégie d’accès des utilisateurs externes à un utilisateur prenant en charge Skype entreprise

Si un utilisateur a été activé pour Skype entreprise Server, vous pouvez configurer la Fédération SIP, l’accès des utilisateurs distants et la connectivité PIC dans le panneau de configuration de Skype entreprise Server en appliquant les stratégies appropriées à des utilisateurs spécifiques. Par exemple, si vous avez créé une stratégie pour prendre en charge l’accès des utilisateurs distants, vous devez l’appliquer à l’utilisateur avant de pouvoir se connecter à Skype entreprise Server à partir d’un emplacement distant et collaborer avec les utilisateurs internes à partir de l’emplacement distant.


> [!NOTE]  
> Pour prendre en charge l’accès des utilisateurs externes, vous devez activer la prise en charge pour chaque type d’accès d’utilisateur externe à prendre en charge, puis configurer les stratégies appropriées et d’autres options afin de contrôler son utilisation. Pour plus d’informations, reportez-vous à la rubrique gestion de la [Fédération et de l’accès externe à Skype entreprise Server](../managing-federation-and-external-access.md).


La procédure de cette rubrique vous permet d’appliquer une stratégie d’accès des utilisateurs externes créée précédemment à un ou plusieurs comptes d’utilisateurs.


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>Pour appliquer une stratégie d’utilisateur externe à un compte d’utilisateur

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Skype entreprise Server. 

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur que vous souhaitez configurer.

4.  Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans **modifier l’utilisateur de Skype entreprise Server** sous **stratégie d’accès externe**, sélectionnez la stratégie utilisateur que vous souhaitez appliquer.
     
> [!NOTE]  
> Les paramètres de ** \<>automatique** appliquent les paramètres de stratégie globale ou de serveur par défaut.


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>Affectation de stratégies d’accès externe par utilisateur à l’aide d’applets de commande Windows PowerShell

Les stratégies d’accès externe par utilisateur peuvent être affectées à l’aide de Windows PowerShell et de l’applet de commande Grant-CsExternalAccessPolicy. Cette applet de commande peut être exécutée à partir de Skype entreprise Server Management Shell ou à partir d’une session distante de Windows PowerShell. 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>Pour affecter une stratégie d’accès externe par utilisateur à un seul utilisateur

  - Cette commande permet d’affecter la stratégie d’accès externe par utilisateur RedmondExternalAccessPolicy à l’utilisateur Ken Myer.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>Pour affecter une stratégie d’accès externe par utilisateur à plusieurs utilisateurs

  - Cette commande permet d’affecter la stratégie d’accès externe par utilisateur USAExternalAccessPolicy à tous les utilisateurs qui possèdent des comptes dans l’unité d’organisation (OU) UnitedStates dans Active Directory. Pour plus d’informations sur le paramètre OU utilisé dans cette commande, reportez-vous à la documentation de la cmdlet [Get-Csuser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) .
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a>Pour annuler l’affectation d’une stratégie d’accès externe par utilisateur

  - Cette commande annule l’affectation d’une stratégie d’accès externe par utilisateur précédemment affectée à Ken Myer. Lorsque cette stratégie par utilisateur n’est plus affectée à Ken Myer, celui-ci est automatiquement géré par la stratégie globale ou, le cas échéant, par la stratégie de site locale associée. La stratégie de site est prioritaire sur la stratégie globale.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null



Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy) .


