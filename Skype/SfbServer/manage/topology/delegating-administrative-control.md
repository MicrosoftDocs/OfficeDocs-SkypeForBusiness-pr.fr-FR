---
title: Déléguer le contrôle administratif de Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: 5c295ed1233cb8a0900828cb1d1c074de1d0f16f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817270"
---
# <a name="delegate-administrative-control-of-skype-for-business-server"></a>Déléguer le contrôle administratif de Skype entreprise Server 

Dans Skype entreprise Server, les tâches d’administration sont déléguées aux utilisateurs à l’aide de la fonctionnalité de contrôle d’accès basée sur les rôles (RBAC). Lorsque vous installez Skype entreprise Server, de nombreux rôles RBAC sont créés pour vous. Ces rôles correspondent aux groupes de sécurité universelles dans les services de domaine Active Directory. Par exemple, le rôle RBAC CsHelpDesk correspond au groupe CsHelpDesk figurant dans le conteneur utilisateurs dans les services de domaine Active Directory (AD FS). En outre, chaque rôle RBAC est associé à un ensemble de cmdlets Windows PowerShell Skype entreprise Server. Ces applets de contrôle représentent les tâches qui peuvent être effectuées par les utilisateurs auxquels le rôle RBAC donné a été attribué. Par exemple, le rôle CsHelpDesk a été affecté aux cmdlets Lock-CsClientPin et UnlockCsClientPin. Cela signifie que les utilisateurs qui ont été attribués au rôle CsHelpDesk peuvent verrouiller ou déverrouiller des numéros de broche d’utilisateur. Toutefois, le rôle CsHelpDesk n’a pas été affecté à l’applet de nouvelle applet de nouveau CsVoicePolicy. Cela signifie que les utilisateurs qui ont été affectés au rôle CsHelpDesk ne peuvent pas créer de nouvelles stratégies vocales.

## <a name="viewing-information-about-rbac-roles"></a>Affichage d’informations sur les rôles RBAC

Vous pouvez récupérer des informations de base sur vos rôles RBAC en exécutant la commande suivante à partir de Skype entreprise Server Management Shell :

`Get-CsAdminRole`

Gardez à l’esprit que l’identité du rôle RBAC (par exemple, CsVoiceAdministrator) est associée à un groupe de sécurité figurant dans le conteneur utilisateurs dans les services de domaine Active Directory (AD DS).

Pour afficher une liste des applets de commande attribuées à un rôle, utilisez une commande semblable à celle-ci :

`Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets`

## <a name="assigning-an-rbac-role-to-a-user"></a>Attribution d’un rôle RBAC à un utilisateur

Pour attribuer un rôle RBAC à un utilisateur, vous devez l’ajouter au groupe de sécurité Active Directory approprié. Par exemple, pour affecter le rôle CsLocationAdministrator à un utilisateur, vous devez ajouter cet utilisateur au groupe CsLocationAdministrator. Pour cela, procédez comme suit :

1. À l’aide d’un compte qui dispose des autorisations nécessaires pour modifier l’appartenance à un groupe Active Directory, connectez-vous à un ordinateur sur lequel sont installés les utilisateurs et ordinateurs Active Directory.
2. Cliquez sur **Démarrer**, sur **tous les programmes**, sur **Outils d’administration**, puis sur **utilisateurs et ordinateurs Active Directory**.
3. Dans utilisateurs et ordinateurs Active Directory, développez le nom de votre domaine, puis cliquez sur le conteneur **utilisateurs** .
4. Cliquez avec le bouton droit sur le groupe de sécurité **CsLocationAdministrator**, puis cliquez sur **Propriétés**.
5. Dans la boîte de dialogue **Propriétés** , sous l’onglet **membres** , cliquez sur **Ajouter**.
6. Dans la boîte de dialogue **Sélectionner des utilisateurs, des ordinateurs, des contacts ou des groupes** , entrez le nom d’utilisateur ou le nom d’affichage de l’utilisateur à ajouter au groupe (par exemple, Ken Myer) dans la zone **Entrez les noms des objets à sélectionner** , puis cliquez sur **OK**.
7. Dans la boîte de dialogue **Propriétés** , cliquez sur **OK**.

Pour vérifier que le rôle RBAC a été affecté, utilisez l’applet de contrôle Get-CsAdminRoleAssignment, en transmettant l’applet de contrôle SamAccountName (nom de connexion Active Directory) de l’utilisateur. Par exemple, exécutez la commande suivante à partir de Skype entreprise Server Management Shell :

`Get-CsAdminRoleAssignment  -Identity "kenmyer"`
