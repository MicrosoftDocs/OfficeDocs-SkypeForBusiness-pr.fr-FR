---
title: Tester les conférences téléphoniques dans Skype Entreprise Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: f4ccbfd4-6075-466f-b459-20561318803d
description: 'Résumé : Découvrez comment tester les conférences téléphoniques dans Skype Entreprise Server.'
ms.openlocfilehash: b6f33828646a8d56574091e296ed5ca4dde75af5
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62385591"
---
# <a name="test-dial-in-conferencing-in-skype-for-business-server"></a>Tester les conférences téléphoniques dans Skype Entreprise Server
 
**Résumé :** Découvrez comment tester les conférences téléphoniques dans Skype Entreprise Server.
  
Pour terminer la vérification de votre configuration de conférence rendez-vous, vous pouvez chercher des plans de numérotation dont la région de conférence rendez-vous n’est utilisée par aucun numéro d’accès et des numéros d’accès que vous n’avez pas spécifiés dans une région de conférence rendez-vous. Vous devez également vérifier que la page web de conférence Paramètres et les numéros d’accès aux conférences téléphoniques fonctionnent correctement.
  
## <a name="find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a>Rechercher des plans de numérotation avec une région de conférence rendez-vous qui n’est pas utilisée par un numéro d’accès

1. Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou membre du rôle Cs-ServerAdministratorr ou CsAdministrator.
    
2. Démarrez l Skype Entreprise Server Management Shell : cliquez sur **Démarrer, sur** Tous les **programmes, sur** **Skype Entreprise 2015**, puis sur Skype Entreprise Server **Management Shell**.
    
3. Exécutez la commande suivante à l’invite de commandes :
    
   ```PowerShell
   Get-CsDialinConferencingAccessNumber -EmptyRegion
   ```

    Cette applet de commande retourne tous les plans de numérotation dont la région de conférence rendez-vous n’est pas utilisée par un numéro d’accès.
    
Pour plus d’informations, [voir Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).
  
## <a name="find-access-numbers-without-assigned-regions"></a>Rechercher des numéros d’accès sans régions affectées

1. Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou membre du rôle Cs-ServerAdministratorr ou CsAdministrator.
    
2. Démarrez l Skype Entreprise Server Management Shell : cliquez sur **Démarrer, sur** Tous les **programmes, sur** **Skype Entreprise 2015**, puis sur Skype Entreprise Server **Management Shell**.
    
3. Exécutez la commande suivante à l’invite de commandes :
    
   ```PowerShell
   Get-CsDialinConferencingAccessNumber -Region NULL
   ```

    Cette applet de commande retourne tous les numéros d’accès de conférences rendez-vous qui ne sont pas associés à une région.
    
Pour plus d’informations, [voir Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).
  
## <a name="test-webpage-and-access-numbers"></a>Tester les numéros de page web et d’accès

Pour vérifier que la page web Paramètres de conférence rendez-vous et les numéros d’accès entrants fonctionnent correctement, vous devez :
  
- tester la page web Paramètres de conférence rendez-vous en vous connectant à l’URL simple ;
    
- tester les numéros d’accès d’un pool spécifique en exécutant le script présenté plus loin dans cette rubrique. Ce script simule les appels vers les numéros d’accès. Pour l’utiliser, vous devez disposer de l’adresse SIP et des informations d’identification de l’un des clients de communications unifiées hébergés sur le pool.
    
### <a name="to-test-access-numbers-for-a-specific-pool"></a>Pour tester les numéros d’accès à un pool spécifique

1. Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou membre du rôle Cs-ServerAdministratorr ou CsAdministrator.
    
2. Démarrez l Skype Entreprise Server Management Shell : cliquez sur **Démarrer, sur** Tous les **programmes, sur** **Skype Entreprise 2015**, puis sur Skype Entreprise Server **Management Shell**.
    
3. Exécutez la commande suivante à l’invite de commandes :
    
   ```PowerShell
   $credentials = Get-Credential
   User name:  testuser1@contoso.com
   Password:  ********
   Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
   ```

    Le rapport obtenu indique Opération réussie ou Échec ainsi que des informations de diagnostic. L’indicateur -Verbose fournit des informations plus détaillées sur le nombre de numéros d’accès trouvés et des détails les concernant.
    
Pour plus d’informations, [voir Test-CsDialInConferencing](/powershell/module/skype/test-csdialinconferencing?view=skype-ps).
