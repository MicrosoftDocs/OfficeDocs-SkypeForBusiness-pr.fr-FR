---
title: Déléguer le contrôle administratif des Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: ''
ms.openlocfilehash: 1ee1cdce6bae163ea51ebb73ac9b536e75b204a8
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743420"
---
# <a name="delegate-administrative-control-of-skype-for-business-server"></a>Déléguer le contrôle administratif des Skype Entreprise Server 

Dans Skype Entreprise Server, les tâches administratives sont déléguées aux utilisateurs à l’aide de la fonctionnalité de contrôle d’accès basé sur un rôle (RBAC). Lorsque vous installez Skype Entreprise Server, un certain nombre de rôles RBAC sont créés pour vous. Ces rôles correspondent aux groupes de sécurité universels dans les services de domaine Active Directory. Par exemple, le rôle RBAC CsHelpDesk correspond au groupe CsHelpDesk trouvé dans le conteneur Utilisateurs des services de domaine Active Directory. En outre, chaque rôle RBAC est associé à un ensemble d’Skype Entreprise ServerWindows PowerShell cmdlets.   Ces cmdlets représentent les tâches qui peuvent être effectuées par les utilisateurs qui ont reçu le rôle RBAC donné. Par exemple, le rôle CsHelpDesk a reçu les cmdlets Lock-CsClientPin et UnlockCsClientPin. Cela signifie que les utilisateurs qui ont reçu le rôle CsHelpDesk peuvent verrouiller et déverrouiller les numéros de code confidentiel de l’utilisateur. Cependant, l’applet de commande New-CsVoicePolicy n’a pas été affectée au rôle CsHelpDesk. Par conséquent, les utilisateurs auxquels le rôle CsHelpDesk a été affecté ne peuvent pas créer de nouvelles stratégies de voix.

## <a name="viewing-information-about-rbac-roles"></a>Affichage d’informations sur les rôles RBAC

Vous pouvez récupérer des informations de base sur vos rôles RBAC en exécutant la commande suivante à partir de Skype Entreprise Server Management Shell :

`Get-CsAdminRole`

N’oubliez pas que l’identité du rôle RBAC (par exemple, CsVoiceAdministrator) a un mappage direct à un groupe de sécurité trouvé dans le conteneur Utilisateurs dans les services de domaine Active Directory.

Pour obtenir une liste des applets de commande qui sont affectées à un rôle, utilisez une commande similaire à celle-ci :

`Get-CsAdminRole -Identity "CsHelpDesk" | Select-Object -ExpandProperty Cmdlets`

## <a name="assigning-an-rbac-role-to-a-user"></a>Attribution d’un rôle RBAC à un utilisateur

Pour attribuer un rôle RBAC à un utilisateur, vous devez l’ajouter au groupe de sécurité Active Directory approprié. Par exemple, pour affecter le rôle CsLocationAdministrator à un utilisateur, vous devez ajouter cet utilisateur au groupe CsLocationAdministrator. Pour cela, effectuez la procédure suivante :

1. En utilisant un compte qui est autorisé à modifier l’appartenance à un groupe Active Directory, connectez-vous à l’ordinateur où Utilisateurs et ordinateurs Active Directory est installé.
2. Cliquez sur **Démarrer**, sur **Tous les programmes**, sur **Outils d’administration**, puis sur **Utilisateurs et ordinateurs Active Directory**.
3. Dans Utilisateurs et ordinateurs Active Directory, développez le nom de votre domaine et cliquez sur le conteneur **Utilisateurs**.
4. Cliquez avec le bouton droit sur le groupe de sécurité **CsLocationAdministrator**, puis cliquez sur **Propriétés**.
5. Dans la boîte de dialogue **Propriétés**, sous l’onglet **Membres**, cliquez sur **Ajouter**.
6. Dans la boîte de dialogue Sélectionner des utilisateurs, des ordinateurs, des **contacts** ou des groupes, tapez le nom  d’utilisateur ou le nom complet de l’utilisateur à ajouter au groupe (par exemple, Ken Myer) dans la zone Entrer les noms des objets à sélectionner, puis cliquez sur **OK**.
7. Dans la boîte de dialogue **Propriétés**, cliquez sur **OK**.

Pour vérifier que le rôle RBAC a été affecté, utilisez l’applet de commande Get-CsAdminRoleAssignment, en indiquant le nom SamAccountName (nom de connexion Active Directory) de l’utilisateur. Par exemple, exécutez cette commande à partir de Skype Entreprise Server Management Shell :

`Get-CsAdminRoleAssignment  -Identity "kenmyer"`
