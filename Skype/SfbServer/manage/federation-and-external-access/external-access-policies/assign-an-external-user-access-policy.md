---
title: Attribuer une stratégie d’accès utilisateur externe
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Si un utilisateur a été activé pour Skype pour Business Server, vous pouvez configurer la fédération SIP, l’accès des utilisateurs distants et solution PIC (PIC) dans le Skype pour le panneau de configuration serveur Business en appliquant les stratégies appropriées à des utilisateurs spécifiques.
ms.openlocfilehash: 3498b7aabaddc80053efca70b89198c224147c0e
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222841"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a>Affecter une stratégie d’accès utilisateur externe à un Skype pour un utilisateur activé

Si un utilisateur a été activé pour Skype pour Business Server, vous pouvez configurer la fédération SIP, l’accès des utilisateurs distants et solution PIC (PIC) dans le Skype pour le panneau de configuration serveur Business en appliquant les stratégies appropriées à des utilisateurs spécifiques. Par exemple, si vous avez créé une stratégie pour prendre en charge l’accès des utilisateurs distants, vous devez l’appliquer à l’utilisateur avant que l’utilisateur peut se connecter à Skype pour Business Server à partir d’un emplacement distant et collaborer avec des utilisateurs internes à partir de l’emplacement distant.


> [!NOTE]  
> Pour prendre en charge l’accès des utilisateurs externes, vous devez activer la prise en charge pour chaque type d’accès utilisateur externe que vous souhaitez prendre en charge et configurer les stratégies appropriées et autres options permettant de contrôler son utilisation. Pour plus d’informations, voir [Managing fédération et accès externe aux Skype pour Business Server](../managing-federation-and-external-access.md).


Utilisez la procédure de cette rubrique pour appliquer une stratégie d’accès des utilisateurs externes créée précédemment à un ou plusieurs comptes d’utilisateurs.


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>Pour appliquer une stratégie d’utilisateur externe à un compte d’utilisateur

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur à configurer.

4.  Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans **Modifier les Skype pour l’utilisateur Business Server** sous **stratégie d’accès externe**, sélectionnez la stratégie d’utilisateur que vous souhaitez appliquer.
     
> [!NOTE]  
> Le ** \<automatique >** paramètres s’appliquent les paramètres de stratégie globale ou de serveur par défaut.


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>Affectation de stratégies d’accès externe par utilisateur à l’aide des applets de commande Windows PowerShell

Stratégies d’accès externe par utilisateur peuvent être affectés à l’aide de Windows PowerShell et l’applet de commande Grant-CsExternalAccessPolicy. Cette applet de commande peut être exécutée à partir de la Skype pour Business Server Management Shell ou à partir d’une session à distance de Windows PowerShell. 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>Pour affecter une stratégie d’accès externe par utilisateur à un utilisateur unique

  - Cette commande attribue la stratégie d’accès externe par utilisateur RedmondExternalAccessPolicy à l’utilisateur Ken Myer.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>Pour affecter une stratégie d’accès externe par utilisateur à plusieurs utilisateurs

  - Cette commande attribue la stratégie d’accès externe par utilisateur USAExternalAccessPolicy à tous les utilisateurs qui disposent de comptes dans l’unité d’organisation des États-Unis dans Active Directory. Pour plus d’informations sur le paramètre d’unité d’organisation utilisé dans cette commande, voir la documentation de l’applet de commande [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) .
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a>Pour annuler l’affectation d’une stratégie d’accès externe par utilisateur

  - Cette commande annule toute stratégie d’accès externe par utilisateur préalablement attribuée à Ken Myer. Une fois l’affectation de la stratégie par utilisateur annulée, Ken Myer sera automatiquement géré en utilisant la stratégie globale ou, le cas échéant, sa stratégie de site local. Une stratégie de site est prioritaire sur la stratégie globale.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null



Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy) .


