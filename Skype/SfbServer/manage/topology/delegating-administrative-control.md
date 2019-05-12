---
title: Déléguer le contrôle administratif de Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: b8da2577140ca901c31b94c4b9987f2addef7bba
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924835"
---
# <a name="delegate-administrative-control-of-skype-for-business-server"></a>Déléguer le contrôle administratif de Skype pour Business Server 

Dans Skype pour Business Server, les tâches d’administration sont déléguées aux utilisateurs à l’aide de la fonctionnalité de contrôle (RBAC) d’accès basé sur un rôle. Lorsque vous installez Skype pour Business Server, un nombre de rôles RBAC est créé pour vous. Ces rôles correspondent aux groupes de sécurité universels dans les Services de domaine Active Directory. Par exemple, le rôle RBAC est CsHelpDesk correspond au groupe est CsHelpDesk trouvé dans le conteneur utilisateurs dans les Services de domaine Active Directory. En outre, chaque rôle RBAC est associé à un ensemble de Skype pour les applets de commande Windows PowerShell Business Server. Ces applets de commande représentent les tâches qui peuvent être exécutées par les utilisateurs auxquels le rôle RBAC donné ont été affectés. Par exemple, le rôle CsHelpDesk a été affecté les applets de commande UnlockCsClientPin Lock-CsClientPin. Cela signifie que les utilisateurs qui ont été affectés le rôle CsHelpDesk peuvent verrouiller et déverrouiller des numéros de code confidentiel utilisateur. Toutefois, le rôle CsHelpDesk n'a pas été affecté l’applet de commande New-CsVoicePolicy. Cela signifie que les utilisateurs qui ont été affectés le rôle CsHelpDesk ne peut pas créer de nouvelles stratégies de voix.

## <a name="viewing-information-about-rbac-roles"></a>Affichage des informations sur les rôles RBAC

Vous pouvez récupérer des informations de base sur les rôles RBAC en exécutant la commande suivante à partir de la Skype pour Business Server Management Shell :

`Get-CsAdminRole`

N’oubliez pas que l’identité du rôle RBAC (par exemple, CsVoiceAdministrator) correspond à un groupe de sécurité dans le conteneur utilisateurs dans les Services de domaine Active Directory.

Pour afficher une liste des applets de commande qui ont été affectés à un rôle, utilisez une commande similaire à celle-ci :

`Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets`

## <a name="assigning-an-rbac-role-to-a-user"></a>Affectation d’un rôle RBAC à un utilisateur

Pour attribuer un rôle RBAC à un utilisateur, vous devez ajouter cet utilisateur au groupe de sécurité Active Directory approprié. Par exemple, pour attribuer le rôle CsLocationAdministrator à un utilisateur, vous devez ajouter cet utilisateur au groupe CsLocationAdministrator. Qui peuvent être effectuées en procédant comme suit :

1. À l’aide d’un compte qui est autorisé à modifier l’appartenance à un groupe Active Directory, ouvrez une session sur un ordinateur où les utilisateurs d’Active Directory et des ordinateurs a été installé.
2. Cliquez sur **Démarrer**, sur **Tous les programmes**, sur **Outils d’administration**, puis cliquez sur **utilisateurs et ordinateurs**.
3. Dans utilisateurs et ordinateurs, développez le nom de votre domaine, cliquez sur le conteneur **utilisateurs** .
4. Cliquez sur le groupe de sécurité **CsLocationAdministrator**, puis cliquez sur **Propriétés**.
5. Dans la boîte de dialogue **Propriétés** , sous l’onglet **membres** , cliquez sur **Ajouter**.
6. Dans la boîte de dialogue **Sélectionner des utilisateurs, des ordinateurs, des Contacts ou des groupes** , tapez le nom d’utilisateur ou nom complet de l’utilisateur à ajouter au groupe (par exemple, Ken Myer) dans la zone **Entrez les noms des objets à sélectionner** , puis cliquez sur **OK**.
7. Dans la boîte de dialogue **Propriétés** , cliquez sur **OK**.

Pour vérifier que le rôle RBAC a été assigné, utilisez l’applet de commande Get-CsAdminRoleAssignment, en passant l’applet de commande SamAccountName (nom d’ouverture de session Active Directory) de l’utilisateur. Par exemple, exécutez cette commande à partir de la Skype pour Business Server Management Shell :

`Get-CsAdminRoleAssignment  -Identity "kenmyer"`
