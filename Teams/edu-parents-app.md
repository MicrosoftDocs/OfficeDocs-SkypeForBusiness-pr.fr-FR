---
title: Configurer l’administrateur pour l’application Microsoft Parents pour l’éducation
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Microsoft Teams d’article pour l’ÉDUCATION - Conditions préalables et configurer PowerShell pour l’application Parents.
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9ca2c252964f610ee13924f25f5d4ca8e31b9d59
ms.sourcegitcommit: 4a9ea18808d17e2eb6e4e2e7e3894e33c14e8631
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/22/2021
ms.locfileid: "59475907"
---
# <a name="deploying-the-parents-app-in-microsoft-teams"></a>Déploiement de l’application parents dans Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

L’activation de l’application Parents dans Microsoft Teams est un processus simple pour les administrateurs, qui offre aux enseignants une méthode sécurisée pour communiquer à leurs étudiants et à leurs contacts qui restent au sein du client, et qui s’adressera à l’ensemble de votre organisation de formateurs.

## <a name="requirements"></a>Conditions requises

- SDS (School data sync) : vous devrez charger dans SDS les contacts associés associés à vos étudiants à l’aide de l’option CSV. Pour plus [d’informations,](/schooldatasync/set-up-your-sds-flow) voir Configurer le CSV pour SDS et Mettre à jour [relatedContacts.](/graph/api/relatedcontact-update)
- Dans Teams d’administration, le propriétaire  de la classe  doit avoir activé la conversation et la conversation fédérée avec Teams non la gestion par **une organisation.**

Si vous avez besoin d’activer la conversation fédérée par utilisateur, les étapes ci-dessous sont ci-dessous.

## <a name="enabling-federated-chat-on-a-per-user-basis"></a>Activation d’une conversation fédérée par utilisateur

1. Installez la dernière version Microsoft Teams prévisualisation du module PowerShell.

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force -AllowClobber
    ```
    
2. Exécuter dans une fenêtre de commande à l’aide d’informations d’identification qui ont des privilèges d’administrateur.

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```
    
3. Désactiver et activer la configuration au niveau global du groupe/de l’utilisateur ou de la configuration au niveau du client.

    ```powershell
    #Retrieves tenant level configuration
    Get-CsTenantFederationConfiguration
    #Turn OFF tenant level configuration
    Set-CsTenantFederationConfiguration -AllowTeamsConsumer $false
    #Turn ON tenant level configuration
    Set-CsTenantFederationConfiguration -AllowTeamsConsumer $true
    #Turn OFF Global GROUP/USER level configuration
    Set-CsExternalAccessPolicy -EnableTeamsConsumerAccess $false
    #Turn ON Global GROUP/USER level configuration
    Set-CsExternalAccessPolicy -EnableTeamsConsumerAccess $false
    ```
        
    > [!NOTE]
    > Lors de l’exécution de cette powerShell, les modifications peuvent prendre au moins une heure.
    
## <a name="more-information"></a>Plus d’informations

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [Affectation de votre stratégie à un utilisateur](/powershell/module/skype/grant-csexternalaccesspolicy)
