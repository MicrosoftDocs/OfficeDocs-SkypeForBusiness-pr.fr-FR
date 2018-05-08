---
title: Configuration des paramètres de parcage d’appel dans Skype Entreprise 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
description: Modifier les paramètres de parcage d’appel dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: 8f4aa5025cbe364a44a45632ebcdf852ad6a65bc
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="configure-call-park-settings-in-skype-for-business-2015"></a>Configuration des paramètres de parcage d’appel dans Skype Entreprise 2015
 
Modifier les paramètres de parcage d’appel dans Skype pour Business Server Enterprise Voice.
  
Si vous ne souhaitez pas utiliser les paramètres de parcage d’appel par défaut, vous pouvez les personnaliser. Lorsque vous installez l’application de parcage d’appel, les paramètres globaux sont configurés par défaut. Vous pouvez modifier les paramètres généraux et définir également des paramètres spécifiques à un site. Utilisez l’applet de commande **New-CsCpsConfiguration** pour créer des paramètres spécifiques au site. Utilisez l’applet de commande **Set-CsCpsConfiguration** pour modifier les paramètres existants.
  
> [!NOTE]
> Nous vous recommandons de configurer au moins l’option **OnTimeoutURI** pour la destination de remplacement à utiliser lorsqu’un appel parqué échoue.
  
Utilisez l’applet de commande **New-CsCpsConfiguration** ou l’applet de commande **Set-CsCpsConfiguration** pour configurer les paramètres suivants :
  
|**Cette option :**|**Définit ceci :**|
|:-----|:-----|
|**CallPickupTimeoutThreshold** <br/> |Période qui s’écoule entre le moment où un appel est parqué et le moment où il sonne de nouveau sur le téléphone auquel il était destiné.  <br/> La valeur doit être entrée au format hh:mm:ss (heures, minutes, secondes). La valeur minimale est de 10 secondes et la valeur maximale, de 10 minutes. La valeur par défaut est 00:01:30.  <br/> |
|**Propriété EnableMusicOnHold** <br/> |Si une musique est diffusée pour l’appelant pendant le parcage d’un appel.  <br/> Les valeurs sont True ou False. La valeur par défaut est True.  <br/> |
|**MaxCallPickupAttempts** <br/> |Nombre de sonnerie de rappel d’un appel parqué avant qu’il soit transféré vers l’URI de remplacement spécifié pour le paramètre **OnTimeoutURI**. La valeur par défaut est 1.<br/> |
|**OnTimeoutURI** <br/> |Adresse SIP (Session Initiation Protocol) de l’utilisateur ou groupe Response Group vers laquelle l’appel parqué sans réponse est routé lorsque la valeur **MaxCallPickupAttempts** est atteinte. <br/> La valeur doit être une URI SIP (Session Initiation Protocol) et commencer par la chaîne « sip: ». Par exemple, sip:bob@contoso.com. La valeur par défaut est aucune adresse de transfert.<br/> |
   
### <a name="to-configure-call-park-settings"></a>Pour configurer les paramètres de parcage d’appel

1. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
2. Exécutez :
    
   ```
   New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
   ```

   > [!TIP]
   > Utilisez l’applet de commande **Get-CsSite** pour identifier le site. Pour plus d’informations, voir la documentation Lync Server Management Shell.
  
    Par exemple :
    
   ```
   New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com
   ```

## <a name="see-also"></a>Voir aussi

#### 

[Personnaliser une musique de parcage d’appel d’attente inSkype pour Business 2015](customize-call-park-music-on-hold.md)
#### 

[Nouvelle-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscpsconfiguration?view=skype-ps)
  
[Set-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscpsconfiguration?view=skype-ps)
  
[Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps)

