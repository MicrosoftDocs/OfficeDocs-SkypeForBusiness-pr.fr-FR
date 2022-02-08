---
title: Attribution d’une stratégie d’accès des utilisateurs externes
ms.reviewer: ''
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Si un utilisateur a été activé pour Skype Entreprise Server, vous pouvez configurer la fédération SIP, l’accès des utilisateurs distants et la connectivité de messagerie instantanée publique dans le Panneau de configuration Skype Entreprise Server en appliquant les stratégies appropriées à des utilisateurs spécifiques.
ms.openlocfilehash: 7430cbe015802d377e4d0ca2f1159006a9951a4f
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62395246"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a>Affecter une stratégie d’accès des utilisateurs externes à Skype Entreprise utilisateur activé

Si un utilisateur a été activé pour Skype Entreprise Server, vous pouvez configurer la fédération SIP, l’accès des utilisateurs distants et la connectivité de messagerie instantanée publique dans le Panneau de configuration Skype Entreprise Server en appliquant les stratégies appropriées à des utilisateurs spécifiques. Par exemple, si vous avez créé une stratégie pour prendre en charge l’accès des utilisateurs distants, vous devez l’appliquer à l’utilisateur pour qu’il puisse se connecter à Skype Entreprise Server à partir d’un emplacement distant et collaborer avec des utilisateurs internes à partir de l’emplacement distant.


> [!NOTE]  
> Pour prendre en charge l’accès des utilisateurs externes, vous devez activer la prise en charge pour chaque type d’accès d’utilisateur externe à prendre en charge, puis configurer les stratégies appropriées et d’autres options afin de contrôler son utilisation. Pour plus d’informations, voir [Managing federation and external access to Skype Entreprise Server](../managing-federation-and-external-access.md).


La procédure de cette rubrique vous permet d’appliquer une stratégie d’accès des utilisateurs externes créée précédemment à un ou plusieurs comptes d’utilisateurs.


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>Pour appliquer une stratégie d’utilisateur externe à un compte d’utilisateur

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur que vous souhaitez configurer.

4.  Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.

5.  Dans **Modifier Skype Entreprise Server utilisateur sous Stratégie** **d’accès** externe, sélectionnez la stratégie utilisateur à appliquer.
     
> [!NOTE]  
> Les paramètres **\<Automatic>** appliquent les paramètres de stratégie globale ou serveur par défaut.


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>Affectation de Per-User d’accès externe à l’aide Windows PowerShell cmdlets

Les stratégies d’accès externe par utilisateur peuvent être affectées à l’Windows PowerShell et à l'Grant-CsExternalAccessPolicy d’accès. Cette cmdlet peut être exécuté à partir de l’Skype Entreprise Server Management Shell ou d’une session distante de Windows PowerShell. 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>Pour affecter une stratégie d’accès externe par utilisateur à un seul utilisateur

  - Cette commande permet d’affecter la stratégie d’accès externe par utilisateur RedmondExternalAccessPolicy à l’utilisateur Ken Myer.<br/><br/>Grant-CsExternalAccessPolicy -Identity « Ken Myer » -PolicyName « RedmondExternalAccessPolicy »


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>Pour affecter une stratégie d’accès externe par utilisateur à plusieurs utilisateurs

  - Cette commande permet d’affecter la stratégie d’accès externe par utilisateur USAExternalAccessPolicy à tous les utilisateurs qui possèdent des comptes dans l’unité d’organisation (OU) UnitedStates dans Active Directory. Pour plus d’informations sur le paramètre OU utilisé dans cette commande, consultez la documentation de l';cmdlet [Get-CsUser](/powershell/module/skype/Get-CsUser) .<br/><br/>Get-CsUser -OU « ou=United States,dc=litwareinc,dc=com » | Grant-CsExternalAccessPolicy -PolicyName « USAExternalAccessPolicy »


## <a name="to-unassign-a-per-user-external-access-policy"></a>Pour désattribuer une stratégie d’accès externe par utilisateur

  - Cette commande annule l’affectation d’une stratégie d’accès externe par utilisateur précédemment affectée à Ken Myer. Lorsque cette stratégie par utilisateur n’est plus affectée à Ken Myer, celui-ci est automatiquement géré par la stratégie globale ou, le cas échéant, par la stratégie de site locale associée. La stratégie de site est prioritaire sur la stratégie globale.<br/><br/>Grant-CsExternalAccessPolicy -Identity « Ken Myer » -PolicyName $Null


Pour plus d’informations, voir la rubrique d’aide de l’cmdlet [Grant-CsExternalAccessPolicy](/powershell/module/skype/Grant-CsExternalAccessPolicy) .
