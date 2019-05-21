---
title: Test de la Conférence rendez-vous dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4ccbfd4-6075-466f-b459-20561318803d
description: 'Résumé: Découvrez comment tester les conférences rendez-vous dans Skype entreprise Server.'
ms.openlocfilehash: cd1192950ff7c8b609655d78bbc57dfdbc4c1710
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280361"
---
# <a name="test-dial-in-conferencing-in-skype-for-business-server"></a>Test de la Conférence rendez-vous dans Skype entreprise Server
 
**Résumé:** Découvrez comment tester les conférences rendez-vous dans Skype entreprise Server.
  
Pour terminer la vérification de votre configuration de conférence rendez-vous, vous pouvez chercher des plans de numérotation dont la région de conférence rendez-vous n’est utilisée par aucun numéro d’accès et des numéros d’accès que vous n’avez pas spécifiés dans une région de conférence rendez-vous. Vous devez également vérifier que la page web Paramètres de conférence rendez-vous et les numéros d’accès entrants fonctionnent correctement.
  
## <a name="find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a>Trouver des plans de numérotation dont la région de conférence rendez-vous n’est utilisée par aucun numéro d’accès

1. Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins  ou du rôle Cs-ServerAdministrator  ou CsAdministrator.
    
2. Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
3. Exécutez la commande suivante dans l’invite de commandes :
    
   ```
   Get-CsDialinConferencingAccessNumber -EmptyRegion
   ```

    Cette applet de commande renvoie tous les plans de numérotation dont la région de conférence rendez-vous n’est pas utilisée par un numéro d’accès.
    
Pour plus d’informations, consultez la rubrique [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).
  
## <a name="find-access-numbers-without-assigned-regions"></a>REcherche de numéros d’accès sans région affectée

1. Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins  ou du rôle Cs-ServerAdministrator  ou CsAdministrator.
    
2. Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
3. Exécutez la commande suivante dans l’invite de commandes :
    
   ```
   Get-CsDialinConferencingAccessNumber -Region NULL
   ```

    Cette applet de commande renvoie tous les numéros d’accès de conférences rendez-vous qui ne sont pas associés à une région.
    
Pour plus d’informations, consultez la rubrique [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).
  
## <a name="test-webpage-and-access-numbers"></a>Test de la page web et des numéros d’accès

Pour vérifier que la page web Paramètres de conférence rendez-vous et les numéros d’accès entrants fonctionnent correctement, vous devez :
  
- tester la page web Paramètres de conférence rendez-vous en vous connectant à l’URL simple ;
    
- tester les numéros d’accès d’un pool spécifique en exécutant le script présenté dans la suite de cette rubrique. Ce script simule les appels vers les numéros d’accès. Pour l’utiliser, vous devez disposer de l’adresse SIP et des informations d’identification de l’un des clients de communications unifiées hébergés sur le pool.
    
### <a name="to-test-access-numbers-for-a-specific-pool"></a>Pour tester les numéros d’accès à un pool spécifique

1. Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins  ou du rôle Cs-ServerAdministrator  ou CsAdministrator.
    
2. Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.
    
3. Exécutez la commande suivante dans l’invite de commandes :
    
   ```
   $credentials = Get-Credential
   User name:  testuser1@contoso.com
   Password:  ********
   Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
   ```

    Le rapport obtenu indique Opération réussie ou Échec ainsi que des informations de diagnostic. L’indicateur-verbose fournit des informations plus détaillées sur le nombre de numéros d’accès qui ont été trouvés et leur détails.
    
Pour plus d’informations, consultez la rubrique [test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps).
  

