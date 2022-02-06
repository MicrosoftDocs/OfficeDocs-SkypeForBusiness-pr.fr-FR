---
title: Configurer les paramètres de parcier d’appel dans Skype Entreprise
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
description: Modifiez les paramètres de parc Skype Entreprise Server Voix Entreprise.
---

# <a name="configure-call-park-settings-in-skype-for-business"></a>Configurer les paramètres de parcier d’appel dans Skype Entreprise

Modifiez les paramètres de parc Skype Entreprise Server Voix Entreprise.

Si vous ne souhaitez pas utiliser les paramètres de parcment d’appel par défaut, vous pouvez les personnaliser. Lorsque vous installez l’application de parcage d’appel, les paramètres globaux sont configurés par défaut. Vous pouvez modifier les paramètres globaux et définir également des paramètres spécifiques à un site. L’applet de commande **New-CsCpsConfiguration** permet de créer des paramètres spécifiques à un site. L’applet de commande **Set-CsCpsConfiguration** permet de modifier les paramètres existants.

> [!NOTE]
> Nous vous recommandons de configurer au moins l’option **OnTimeoutURI** pour la destination de remplacement à utiliser lorsqu’un appel parqué échoue.

Les applets de commande **New-CsCpsConfiguration** et **Set-CsCpsConfiguration** permettent de configurer les paramètres suivants :


| **Cette option :**                     | **Définit ceci :**                                                                                                                                                                                                                                                                                                                   |
|:-------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **CallPickupTimeoutThreshold** <br/> | Laps de temps qui s’écoule entre le moment où un appel est parqué et le moment où il sonne de nouveau sur le téléphone auquel il était destiné.  <br/> La valeur doit être entrée au format hh:mm:ss (heures, minutes, secondes). La valeur minimale est de 10 secondes et la valeur maximale est de 10 minutes. La valeur par défaut est 00:01:30.  <br/> |
| **EnableMusicOnHold** <br/>          | Si une musique est diffusée pour l’appelant pendant le parcage d’un appel.  <br/> Les valeurs sont True ou False. La valeur par défaut est True.  <br/>                                                                                                                                                                                                                 |
| **MaxCallPickupAttempts** <br/>      | Nombre de sonnerie de rappel d’un appel parqué avant qu’il ne soit transféré vers l’URI de remplacement spécifié pour le paramètre **OnTimeoutURI**. La valeur par défaut est 1.<br/>                                                                                                                         |
| **OnTimeoutURI** <br/>               | Adresse SIP de l’utilisateur ou groupe Response Group vers laquelle l’appel parqué sans réponse est routé lorsque la valeur **MaxCallPickupAttempts** est atteinte. <br/> La valeur doit être une URI SIP et commencer par la chaîne « sip: ». Par exemple, sip:bob@contoso.com. La valeur par défaut est aucune adresse de transfert.<br/>                                                   |

### <a name="to-configure-call-park-settings"></a>Pour configurer les paramètres de parcment d’appel

1. Démarrez l Skype Entreprise Server Management Shell : cliquez sur **Démarrer, sur** Tous les **programmes, sur** **Skype Entreprise 2015**, puis sur Skype Entreprise Server **Management Shell**.

2. Exécuter : 

   ```powershell
   New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
   ```

   > [!TIP]
   > L’applet de commande **Get-CsSite** permet d’identifier le site. Pour plus d’informations, voir Skype Entreprise Server Management Shell.

    Par exemple :

   ```powershell
   New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com
   ```

## <a name="see-also"></a>Voir aussi

[Personnalisation de l’attente musicale du parc d’appel dansSkype for Business 2015](customize-call-park-music-on-hold.md)

[New-CsCpsConfiguration](/powershell/module/skype/new-cscpsconfiguration?view=skype-ps)

[Set-CsCpsConfiguration](/powershell/module/skype/set-cscpsconfiguration?view=skype-ps)

[Get-CsSite](/powershell/module/skype/get-cssite?view=skype-ps)